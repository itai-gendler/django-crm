---
{
  "kind": "validation",
  "routes": {
    "main": "Create deal — required country missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The inquiry’s department works globally but the required country is absent.",
      "entities": [
        {
          "entity": "country",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Process the inquiry into its commercial opportunity.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Creation is rejected until the configured country prerequisite is met.",
      "entities": [
        {
          "entity": "country",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    }
  ]
}
---

# Create deal — required country missing

## Trigger

Operator invokes Create deal.

## Outcome

Creation is rejected until the configured country prerequisite is met.

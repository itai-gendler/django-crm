---
{
  "kind": "validation",
  "routes": {
    "main": "Create deal — required products missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The applicable department has Products but the inquiry has none selected for Deal creation.",
      "entities": [
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "product",
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
      "text": "Creation is rejected until the applicable departmental product prerequisite is met.",
      "entities": [
        {
          "entity": "product",
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

# Create deal — required products missing

## Trigger

Operator invokes Create deal.

## Outcome

Creation is rejected until the applicable departmental product prerequisite is met.

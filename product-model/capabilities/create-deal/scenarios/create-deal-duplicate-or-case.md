---
{
  "kind": "validation",
  "routes": {
    "main": "Create deal — duplicate or case"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The inquiry is marked Duplicate or Case before commercial processing.",
      "entities": []
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
      "text": "The duplicate/case inquiry cannot create a Deal.",
      "entities": [
        {
          "entity": "deal",
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

# Create deal — duplicate or case

## Trigger

Operator invokes Create deal.

## Outcome

The duplicate/case inquiry cannot create a Deal.

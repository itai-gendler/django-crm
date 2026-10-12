---
{
  "kind": "edge",
  "routes": {
    "main": "Create deal — existing linked deal"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Request already has a linked Deal when commercial processing is invoked.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "request",
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
      "text": "The existing linked Deal is reused without creating another.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Translation",
            "Amount"
          ]
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

# Create deal — existing linked deal

## Trigger

Operator invokes Create deal.

## Outcome

The existing linked Deal is reused without creating another.

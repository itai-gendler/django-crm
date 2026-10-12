---
{
  "kind": "primary",
  "routes": {
    "main": "Edit transaction quality event"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Transaction quality event and invoke edit.",
      "entities": [
        {
          "entity": "transaction-quality-event",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::transaction-quality-event-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Product saves: selected Transaction quality event retains the submitted Signal, Weight, Comment. Source-defined read-only links and attribution remain unchanged.",
      "entities": [
        {
          "entity": "transaction-quality-event",
          "effect": "changes",
          "facts": [
            "Signal",
            "Weight",
            "Comment"
          ]
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::transaction-quality-event-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "quality/models/transaction_quality.py"
    }
  ]
}
---

# Edit transaction quality event

## Trigger

Operator invokes Edit transaction quality event.

## Outcome

The selected Transaction quality event retains the submitted Signal, Weight, Comment. Source-defined read-only links and attribution remain unchanged.

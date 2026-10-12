---
{
  "kind": "primary",
  "routes": {
    "main": "Delete transaction quality event"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Transaction quality event and invoke delete.",
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
      "text": "Remove the selected Transaction quality event.",
      "entities": [
        {
          "entity": "transaction-quality-event",
          "effect": "removes"
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

# Delete transaction quality event

## Trigger

Operator invokes Delete transaction quality event.

## Outcome

Remove the selected Transaction quality event.

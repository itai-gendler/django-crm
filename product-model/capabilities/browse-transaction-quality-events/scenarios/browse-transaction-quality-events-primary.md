---
{
  "kind": "primary",
  "routes": {
    "main": "Browse transaction quality events"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Transaction quality event and invoke browse.",
      "entities": [
        {
          "entity": "transaction-quality-event",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::transaction-quality-event-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Present the source-defined Transaction quality event selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "transaction-quality-event",
          "effect": "reads",
          "facts": [
            "Deal",
            "Signal",
            "Weight",
            "Comment",
            "Created",
            "Modified by"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::transaction-quality-event-browser"
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

# Browse transaction quality events

## Trigger

Operator invokes Browse transaction quality events.

## Outcome

Present the source-defined Transaction quality event selection, search/filter results and summary facts.

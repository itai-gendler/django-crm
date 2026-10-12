---
{
  "kind": "primary",
  "routes": {
    "main": "Create transaction quality event"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save the selected quality signal, retained weight and comment.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Transaction quality event is retained with Deal, Signal, Weight, Comment. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "transaction-quality-event",
          "effect": "creates",
          "facts": [
            "Deal",
            "Signal",
            "Weight",
            "Comment",
            "Created",
            "Modified by"
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
          "place": "crm-web::crm-workspace::deal-record"
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

# Create transaction quality event

## Trigger

Operator invokes Create transaction quality event.

## Outcome

A distinct Transaction quality event is retained with Deal, Signal, Weight, Comment. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

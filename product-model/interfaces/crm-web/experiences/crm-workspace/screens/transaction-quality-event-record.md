---
{
  "entities": [
    {
      "entity": "transaction-quality-event",
      "shows": [
        "Deal",
        "Signal",
        "Weight",
        "Comment",
        "Created",
        "Modified by"
      ],
      "collects": [
        "Signal",
        "Weight",
        "Comment"
      ]
    },
    {
      "entity": "transaction-quality-signal",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "deal",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Filename",
        "Media location"
      ]
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

# Transaction quality event record

Deal, signal, retained weight, comment and attachments.

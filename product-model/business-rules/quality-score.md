---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction-quality-event"
    },
    {
      "type": "entity",
      "id": "transaction-quality-signal"
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

# Quality score

Presented score is 100 plus retained event weights when events exist; no probability interpretation.

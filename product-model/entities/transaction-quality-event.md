---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "quality/models/transaction_quality.py"
    }
  ],
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Transaction quality event

Deal, selected signal, retained weight, comment/date and Files

## Information kept

- **Deal** — Reference to the related commercial relationship.
- **Signal** — Selected configured signal associated with the quality event.
- **Weight** — Retained numeric contribution to the displayed quality score.
- **Comment** — Comment retained with the event.
- **Created** — When the record was created.
- **Modified by** — The account retained as the last modifying person.

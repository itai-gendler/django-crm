---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    }
  ],
  "relations": [
    {
      "entity": "currency-rate",
      "verb": "has dated rate",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Currency

Identity, state/marketing purposes, current conversion information, automatic-update choice and update date

## Information kept

- **Name** — The name used to identify the selected record to people.
- **State currency** — Marks the configured state currency used by the corresponding fallback.
- **Marketing currency** — Marks the configured marketing-purpose currency.
- **Current rates** — Retained current conversion values used by pricing and reporting.
- **Automatic update** — Whether this currency participates in configured rate refresh.
- **Update date** — Date associated with the current conversion values.

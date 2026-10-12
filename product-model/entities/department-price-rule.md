---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/pricingtier.py"
    }
  ]
}
---

# Department price rule

Department, tier name, base-tier flag, fixed/discount/markup type and percentage

## Information kept

- **Department** — The organizational scope retained on this record.
- **Tier name** — The configured Client Type naming this price tier.
- **Base tier** — Tier name used as the base when applying the configured price rule.
- **Price type** — Configured pricing mode, including the base-price choice.
- **Percentage** — Configured price percentage applied to the selected base tier.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

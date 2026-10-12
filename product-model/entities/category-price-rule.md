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

# Category price rule

Product Category, tier name, base-tier flag and calculation information

## Information kept

- **Category** — Selected product category used for classification and category-rule lookup.
- **Tier name** — The configured Client Type naming this price tier.
- **Base tier** — Tier name used as the base when applying the configured price rule.
- **Price type** — Configured pricing mode, including the base-price choice.
- **Percentage** — Configured price percentage applied to the selected base tier.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

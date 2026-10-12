---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/pricingtier.py"
    }
  ],
  "domain": "products"
}
---

# Product price tier

Client Type/tier name, price, minimum quantity, validity dates and description; Product

## Information kept

- **Tier name** — The configured Client Type naming this price tier.
- **Price** — The retained tier/catalog price.
- **Minimum quantity** — Retained minimum quantity; the inspected price lookup does not enforce this threshold.
- **Valid from** — Retained validity-start date; the inspected price lookup does not enforce date eligibility.
- **Valid to** — Retained validity-end date; the inspected price lookup does not enforce date eligibility.
- **Description** — Retained descriptive content.
- **Product** — Reference to the catalog item represented by this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

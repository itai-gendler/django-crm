---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/product.py"
    }
  ],
  "domain": "products",
  "relations": [
    {
      "entity": "product",
      "verb": "classifies",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Product category

Name/body and department; Products and category pricing rules

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Description** — Retained descriptive content.
- **Department** — The organizational scope retained on this record.

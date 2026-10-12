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
      "entity": "product-price-tier",
      "verb": "has tier",
      "cardinality": "one-to-many"
    },
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Product

Name/body, retained price/currency, on-sale flag, goods/service type, category, image and department; tiers and Files

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Description** — Retained descriptive content.
- **Price** — Retained legacy catalog price, displayed by the browser but not collected in the current selected editor.
- **Currency** — Retained legacy catalog currency, displayed by the browser but not collected in the current selected editor.
- **On sale** — Retained legacy sale-availability flag; absent from the current editor fieldsets.
- **Type** — Goods or Service selection.
- **Category** — Selected product category used for classification and price-rule lookup.
- **Image** — Uploaded main catalog image.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product-price-tier"
    },
    {
      "type": "entity",
      "id": "department-price-rule"
    },
    {
      "type": "entity",
      "id": "category-price-rule"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/pricingtier.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/productadmin.py"
    }
  ]
}
---

# Price tier generation

Category rules precede Department rules; base/missing/zero cases differ; existing tier names are skipped.

After native Product save, category rules are selected when present, otherwise department rules. If there is no retained base tier, the first configured base rule creates a zero-priced base tier with a price warning; no base rule yields the missing-rules error. An existing zero base price warns without generating further tiers. Otherwise each missing tier name is generated: discount subtracts its percentage of base price; markup adds it; fixed/other type creates zero with a warning. Existing tier names are skipped. The Product editor reopens with its query string.

---
{
  "actors": [
    "sales-manager"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/productadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/tieredpricinginline.py"
    }
  ]
}
---

# Price new product

## Goal

Price created Product.

## Success criterion

The sales manager saves a new Product with its base pricing control, reaches the retained catalog record and edits the newly generated base tier’s price and eligibility facts.

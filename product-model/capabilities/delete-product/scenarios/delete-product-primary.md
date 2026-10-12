---
{
  "kind": "primary",
  "routes": {
    "main": "Delete product"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Product and invoke delete.",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Remove the selected Product.",
      "entities": [
        {
          "entity": "product",
          "effect": "removes"
        },
        {
          "entity": "product-price-tier",
          "effect": "removes",
          "with": "product"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      },
      "actor": "sales-manager"
    }
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

# Delete product

## Trigger

Sales manager invokes Delete product.

## Outcome

Remove the selected Product.

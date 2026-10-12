---
{
  "kind": "primary",
  "routes": {
    "main": "Browse products"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Product and invoke browse.",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": [
            "Name",
            "Price",
            "Currency",
            "Type",
            "Category"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-browser"
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

# Browse products

## Trigger

Sales manager invokes Browse products.

## Outcome

Present the source-defined Product selection, search/filter results and summary facts.

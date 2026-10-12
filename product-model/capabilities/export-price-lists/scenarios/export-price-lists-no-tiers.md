---
{
  "kind": "edge",
  "routes": {
    "main": "Export price lists — no tiers"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Products have no retained price tiers to export.",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Product and invoke export.",
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
      "text": "The price-list result reports absent tiers rather than inventing prices.",
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

# Export price lists — no tiers

## Trigger

Sales manager invokes Export price lists.

## Outcome

The price-list result reports absent tiers rather than inventing prices.

---
{
  "kind": "primary",
  "routes": {
    "main": "Delete product price tier"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Product price tier and invoke delete.",
      "entities": [
        {
          "entity": "product-price-tier",
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
      "text": "Remove the selected Product price tier.",
      "entities": [
        {
          "entity": "product-price-tier",
          "effect": "removes"
        },
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

# Delete product price tier

## Trigger

Sales manager invokes Delete product price tier.

## Outcome

Remove the selected Product price tier.

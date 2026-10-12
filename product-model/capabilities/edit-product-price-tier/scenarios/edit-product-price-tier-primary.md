---
{
  "kind": "primary",
  "routes": {
    "main": "Edit product price tier"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Product price tier and invoke edit.",
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
      "text": "The selected Product price tier retains the submitted Tier name, Price, Minimum quantity, Valid from, Valid to, Description. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "product-price-tier",
          "effect": "changes",
          "facts": [
            "Tier name",
            "Price",
            "Minimum quantity",
            "Valid from",
            "Valid to",
            "Description",
            "Updated",
            "Modified by"
          ]
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

# Edit product price tier

## Trigger

Sales manager invokes Edit product price tier.

## Outcome

The selected Product price tier retains the submitted Tier name, Price, Minimum quantity, Valid from, Valid to, Description. Read-only fields retain their previous values and invalid form input returns field errors.

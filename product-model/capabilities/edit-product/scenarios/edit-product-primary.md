---
{
  "kind": "primary",
  "routes": {
    "main": "Edit product"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Product and invoke edit.",
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
      "text": "The selected Product retains the submitted Name, Description, Type, Category, Image. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "product",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Type",
            "Category",
            "Image",
            "Department"
          ]
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

# Edit product

## Trigger

Sales manager invokes Edit product.

## Outcome

The selected Product retains the submitted Name, Description, Type, Category, Image. Read-only fields retain their previous values and invalid form input returns field errors.

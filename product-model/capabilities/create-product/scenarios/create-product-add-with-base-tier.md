---
{
  "kind": "primary",
  "routes": {
    "main": "Create product — add with base tier"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Catalog Add submits tier generation with an applicable base rule and no saved base tier.",
      "entities": [
        {
          "entity": "category-price-rule",
          "effect": "reads",
          "facts": [
            "Base tier"
          ]
        },
        {
          "entity": "department-price-rule",
          "effect": "reads",
          "facts": [
            "Base tier"
          ]
        }
      ],
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Save the catalog name, description, goods/service choice, category and image.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The new Product receives its dependent zero-priced base tier and the creator enters tier editing.",
      "entities": [
        {
          "entity": "product",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Price",
            "Currency",
            "On sale",
            "Type",
            "Category",
            "Image",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "product-price-tier",
          "effect": "creates",
          "with": "product",
          "facts": [
            "Tier name",
            "Price",
            "Minimum quantity",
            "Valid from",
            "Valid to",
            "Description",
            "Product",
            "Department",
            "Created",
            "Updated",
            "Modified by"
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

# Create product — add with base tier

## Trigger

Sales manager invokes Create product.

## Outcome

The new Product receives its dependent zero-priced base tier and the creator enters tier editing.

---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      "capability": "create-product",
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
      },
      "capability": "create-product"
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
      "actor": "sales-manager",
      "capability": "create-product"
    },
    {
      "kind": "product",
      "actor": "sales-manager",
      "capability": "create-product",
      "text": "The Product opens the new catalog record containing its generated base tier for editing.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      }
    },
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
      },
      "capability": "edit-product-price-tier"
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
      "actor": "sales-manager",
      "capability": "edit-product-price-tier"
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

# Price new product — new base tier

## Trigger

The sales manager starts by save the catalog name, description, goods/service choice, category and image.

## Outcome

The selected Product price tier retains the submitted Tier name, Price, Minimum quantity, Valid from, Valid to, Description. Read-only fields retain their previous values and invalid form input returns field errors.

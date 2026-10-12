---
{
  "kind": "primary",
  "routes": {
    "main": "Create product"
  },
  "steps": [
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
      "text": "A distinct Product retains the submitted name, description, goods/service selection, category and image. Organizational defaults, modification attribution and dates follow the native save. The legacy monetary fields remain empty and the legacy sale mark starts true; these are not inputs on this form.",
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

# Create product

## Trigger

Sales manager invokes Create product.

## Outcome

A distinct Product retains the submitted name, description, goods/service selection, category and image. Its department, modification attribution and dates follow the native save. Legacy Price and Currency retain their nullable defaults and On sale retains its default; those are not inputs on this form.

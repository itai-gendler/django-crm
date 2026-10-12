---
{
  "kind": "primary",
  "routes": {
    "main": "Export price lists"
  },
  "steps": [
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
      "text": "Produce the workbook projection of the selected Product records.",
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

# Export price lists

## Trigger

Sales manager invokes Export price lists.

## Outcome

Produce the workbook projection of the selected Product records.

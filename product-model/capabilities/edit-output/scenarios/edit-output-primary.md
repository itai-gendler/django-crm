---
{
  "kind": "primary",
  "routes": {
    "main": "Edit output"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Output and invoke edit.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected Output retains its submitted Product, Quantity, Amount, contract/actual shipment dates, serial information and Shipped choice. Its currency follows the containing commercial opportunity.",
      "entities": [
        {
          "entity": "output",
          "effect": "changes",
          "facts": [
            "Product",
            "Quantity",
            "Amount",
            "Currency",
            "Contract shipment date",
            "Actual shipment date",
            "Serial information",
            "Shipped",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/clarify_permission.py"
    }
  ]
}
---

# Edit output

## Trigger

Operator invokes Edit output.

## Outcome

The selected Output retains its submitted Product, Quantity, Amount, contract/actual shipment dates, serial information and Shipped choice. Its currency follows the containing commercial opportunity.

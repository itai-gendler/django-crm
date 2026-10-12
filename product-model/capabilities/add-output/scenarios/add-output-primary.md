---
{
  "kind": "primary",
  "routes": {
    "main": "Add output"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Enter a new commercial line in the selected Deal inline.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name"
          ]
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
      "text": "The Product creates an Output belonging to the selected Deal, with the chosen Product, nonzero quantity, amount, Deal currency and shipment information.",
      "entities": [
        {
          "entity": "output",
          "effect": "creates",
          "facts": [
            "Product",
            "Quantity",
            "Amount",
            "Currency",
            "Planned shipment date",
            "Contract shipment date",
            "Actual shipment date",
            "Serial information",
            "Shipped",
            "Deal",
            "Created",
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
          "entity": "deal",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/outputinline.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/output.py"
    }
  ]
}
---

# Add output

## Trigger

Operator invokes Add output.

## Outcome

The Product creates an Output belonging to the selected Deal, with the chosen Product, nonzero quantity, amount, Deal currency and shipment information.

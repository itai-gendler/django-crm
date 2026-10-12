---
{
  "kind": "primary",
  "routes": {
    "main": "View sales report"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Output and invoke view.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::sales-report"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Output/product projection presents sales calculations using its selected payment and department scope.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": [
            "Product",
            "Quantity",
            "Amount",
            "Currency",
            "Planned shipment date",
            "Contract shipment date",
            "Actual shipment date",
            "Serial information"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::sales-report"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/outputstatadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View sales report

## Trigger

Operator invokes View sales report.

## Outcome

The Output/product projection presents sales calculations using its selected payment and department scope.

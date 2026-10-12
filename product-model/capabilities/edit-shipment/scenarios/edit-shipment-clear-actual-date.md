---
{
  "kind": "primary",
  "routes": {
    "main": "Edit shipment — clear actual date"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The existing Output has an actual shipment date that the editor clears.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
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
          "place": "crm-web::crm-workspace::shipment-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Actual date and shipped flag clear without reversing prior Deal changes.",
      "entities": [
        {
          "entity": "output",
          "effect": "changes",
          "facts": [
            "Planned shipment date",
            "Contract shipment date",
            "Actual shipment date",
            "Serial information",
            "Shipped"
          ]
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::shipment-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/shipmentadmin.py"
    }
  ]
}
---

# Edit shipment — clear actual date

## Trigger

Operator invokes Edit shipment.

## Outcome

Actual date and shipped flag clear without reversing prior Deal changes.

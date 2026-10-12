---
{
  "kind": "primary",
  "routes": {
    "main": "Edit shipment"
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
          "place": "crm-web::crm-workspace::shipment-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Set actual shipment date to mark the Output shipped and update the Deal only when its configured shipment stage differs. Clearing the date does not reverse prior Deal changes.",
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
          "effect": "changes",
          "facts": [
            "Stage",
            "Stage dates",
            "Next step",
            "Next step date"
          ]
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

# Edit shipment

## Trigger

Operator invokes Edit shipment.

## Outcome

Set actual shipment date to mark the Output shipped and update the Deal only when its configured shipment stage differs. Clearing the date does not reverse prior Deal changes.

---
{
  "kind": "primary",
  "routes": {
    "main": "Browse shipments"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Output and invoke browse.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::shipment-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": [
            "Product",
            "Quantity",
            "Contract shipment date",
            "Actual shipment date",
            "Shipped",
            "Deal"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::shipment-browser"
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

# Browse shipments

## Trigger

Operator invokes Browse shipments.

## Outcome

Present the source-defined Output selection, search/filter results and summary facts.

---
{
  "entities": [
    {
      "entity": "output",
      "shows": [
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
      ],
      "collects": [
        "Planned shipment date",
        "Actual shipment date",
        "Serial information"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/output.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/shipmentadmin.py"
    }
  ]
}
---

# Shipment record

Output/Product, quantity, shipment dates, serial information and shipped indication.

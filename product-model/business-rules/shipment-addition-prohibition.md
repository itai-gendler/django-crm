---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "output",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::shipment-record"
        },
        {
          "place": "crm-web::crm-workspace::shipment-browser"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/output.py"
    }
  ],
  "permits": []
}
---

# Shipment addition prohibition

The Shipment projection never permits native Add; Outputs originate through their separately governed Deal/Request paths.

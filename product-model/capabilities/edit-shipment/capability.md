---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/shipmentadmin.py"
    }
  ],
  "domain": "shipments"
}
---

# Edit shipment

Set actual shipment date to mark the Output shipped and update the Deal only when its configured shipment stage differs. Clearing the date does not reverse prior Deal changes.

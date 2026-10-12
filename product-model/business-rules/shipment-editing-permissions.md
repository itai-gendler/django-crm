---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "output",
      "effect": "changes",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/shipmentadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Shipment editing permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native Shipment proxy change permission and actual ShipmentAdmin queryset lookup are required. Only Outputs with a present shipping date enter the queryset. A Manager is limited to Deal owner/co-owner unless also Superoperator, Chief or Superuser; those overlapping privileged roles take precedence. There is no inherited CRM department filter. ShipmentAdmin derives from plain ModelAdmin; it has no BaseModelAdmin ID or ticket search override.

Automatic related Deal stage/follow-up updates follow a permitted Shipment edit, with no independent Deal Change permission call.

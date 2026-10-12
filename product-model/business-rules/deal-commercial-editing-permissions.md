---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal",
      "effect": "changes",
      "facts": [
        "Name",
        "Description",
        "Amount",
        "Currency",
        "Tier name",
        "Discount type",
        "Discount",
        "Stage",
        "Closing reason",
        "Relevant",
        "Active",
        "Owner",
        "Tags"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
        }
      ]
    },
    {
      "type": "entity",
      "id": "deal",
      "effect": "changes",
      "facts": [
        "Stage",
        "Stage dates",
        "Next step",
        "Next step date"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::shipment-record"
        }
      ]
    },
    {
      "type": "entity",
      "id": "deal",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::lead-record"
        }
      ],
      "facts": [
        "Lead",
        "Company",
        "Contact person"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmmodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/clarify_permission.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/basemodeladmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Deal commercial editing permissions

Changes commercial/stage/closing/ownership facts; native change and the ordered ownership and department clarification; chief’s specified commercial fields remain read-only.

Shipment’s automatic related update follows the permitted Shipment proxy edit; it does not call a separate Deal change check. The manager branch uses actual Deal ownership/co-ownership, with no invented department filter.

Lead conversion rewires these references after its Lead change operation. It does not independently request change permission for each linked record.

Clarification accepts administrator, company executive or superoperator first, then an Operator whose selected department matches the object, then the object owner or co-owner. Overlapping role membership preserves this order.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. Ordered clarification accepts Chief, Superoperator or Superuser first; then Operator with matching selected department; then actual owner/co-owner, otherwise refuses. Native Add uses effective Add; native view uses effective View or Change; native change/delete requires its corresponding permission before clarification when an object is supplied.

BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

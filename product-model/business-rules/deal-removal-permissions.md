---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
        },
        {
          "place": "crm-web::crm-workspace::deal-browser"
        }
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

# Deal removal permissions

Removes Deal; native delete and source scope/clarification.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. Ordered clarification accepts Chief, Superoperator or Superuser first; then Operator with matching selected department; then actual owner/co-owner, otherwise refuses. Native Add uses effective Add; native view uses effective View or Change; native change/delete requires its corresponding permission before clarification when an object is supplied.

BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

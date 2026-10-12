---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::lead-record"
        },
        {
          "place": "crm-web::crm-workspace::request-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/lead.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
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

# Lead creation permissions

Native Lead operations: active staff access, configured effective model permission, actual queryset and ordered ownership clarification; conversion/import/helper consequences use their initiating checks

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. Ordered clarification accepts Chief, Superoperator or Superuser first; then Operator with matching selected department; then actual owner/co-owner, otherwise refuses. Native Add uses effective Add; native view uses effective View or Change; native change/delete requires its corresponding permission before clarification when an object is supplied.

BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

Request processing creates a missing Lead after its permitted Request save; it does not invoke an independent native Lead Add check. Imports and conversion use their own initiating paths.

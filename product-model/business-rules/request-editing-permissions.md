---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::request-record"
        }
      ]
    },
    {
      "type": "entity",
      "id": "request",
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
      "target": "crm/models/request.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
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

# Request editing permissions

Native Request creates/reads/changes/removes: active staff access and corresponding configured effective model permission, queryset scope and ordered ownership/department checks where called. Public/API submission is outside these native selectors; source resolution and input checks are behavioral validation

Lead conversion rewires these references after its Lead change operation. It does not independently request change permission for each linked record.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. Ordered clarification accepts Chief, Superoperator or Superuser first; then Operator with matching selected department; then actual owner/co-owner, otherwise refuses. Native Add uses effective Add; native view uses effective View or Change; native change/delete requires its corresponding permission before clarification when an object is supplied.

BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

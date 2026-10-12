---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "company",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::company-record"
        }
      ]
    },
    {
      "type": "entity",
      "id": "company",
      "effect": "changes",
      "facts": [
        "Mailing eligibility"
      ],
      "contexts": [
        {
          "place": "crm-web::public"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/company.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
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
    },
    {
      "actors": [
        "newsletter-recipient"
      ]
    }
  ]
}
---

# Company editing permissions

Native Company operations: active staff access, corresponding configured effective model permission, actual queryset scope and ordered ownership/department checks. Import and bulk transfer use their actual separate paths

Public unsubscribe resolves the registration and writes the linked Company’s eligibility without any additional caller-policy check.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. Ordered clarification accepts Chief, Superoperator or Superuser first; then Operator with matching selected department; then actual owner/co-owner, otherwise refuses. Native Add uses effective Add; native view uses effective View or Change; native change/delete requires its corresponding permission before clarification when an object is supplied.

BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

CompanyAdmin differs from the base search: every nonempty Company search resets its incoming queryset to all Companies before delegating to the base search; Manager/Operator receives its view-only warning. Even ordinary Company text search therefore does not preserve the earlier department-filtered queryset.

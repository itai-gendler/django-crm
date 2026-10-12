---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "payment",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::income-summary"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/models.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Income summary reading permissions

Reads Income Summary’s underlying financial projection; native proxy permission and actual report scope.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

The actual requesting account requires active Staff site access and effective analytics.view_incomestat (native Change is the framework alternative, but this report admin forbids Change). Direct and assigned Group permissions and native Superuser handling are evaluated for that proxy, not the represented base record. AnlModelAdmin inherits selected-department lookup first, otherwise Superoperator assigned department Groups, otherwise base scope; Request proxies additionally exclude Duplicate and Case. Report-specific secondary queries and filters remain part of its projection rather than independent base-record view checks.

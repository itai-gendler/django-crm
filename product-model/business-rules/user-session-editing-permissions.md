---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-session",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace"
        },
        {
          "place": "crm-web::restricted-administration"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/crmsite.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/usermiddleware.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# User session editing permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

The selected instance is request.session belonging to the actual request credential/current account. The handler does not select another Session merely because it belongs to the same User. Public Task completion keeps the outer caller Session distinct from the internally authenticated selected-User client Session.

On non-AJAX requests Superuser/Chief/Superoperator/Accountant use supplied department or current-session selection; all or absence selects no department. Supplied privileged department is not checked for Group membership. Other accounts derive department from their first department Group. AJAX skips this department-setting branch. Report currency switching changes this request.session under the staff wrapper with no independent report-model permission.

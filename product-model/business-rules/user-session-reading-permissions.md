---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-session",
      "effect": "reads",
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

# User session reading permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

The selected instance is request.session belonging to the actual request credential/current account. The handler does not select another Session merely because it belongs to the same User. Public Task completion keeps the outer caller Session distinct from the internally authenticated selected-User client Session.

The current request reads its own selected department and report currency.

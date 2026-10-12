---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-record"
        },
        {
          "place": "crm-web::crm-workspace::email-browser"
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
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/admin_redirect_middleware.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email reading permissions

Native Email disclosure follows its effective model view/change permission and the inherited selected-department queryset. Helper source-message lookup and printing have their own contracts.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Restricted administration Email disclosure additionally passes the route Superuser restriction and native administration access/view or change permission. CRM disclosure retains its actual native lookup and view checks. BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

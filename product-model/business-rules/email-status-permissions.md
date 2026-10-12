---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email",
      "effect": "changes",
      "facts": [
        "Incoming",
        "Sent",
        "Trash"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-record"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email status permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Direct Email Incoming, Sent and Trash edits use the restricted administration route: the initiating account must pass its Superuser redirect restriction and the native administration access/change checks. The CRM Email fieldsets expose none of these flags as submitted editable fields, including for a Superuser. Ordinary send_email changes Sent after an authorized native CRM Email Add or Change save; it needs no separate administrative flag-edit grant, preserves the actual initiating account and is not an unattended or administrator operation.

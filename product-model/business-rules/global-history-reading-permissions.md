---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "history",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::restricted-administration::global-history"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
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

# Global history reading permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

The restricted administration route redirects a non-Superuser to CRM. Global History reading passes that route restriction, native administration access and effective LogEntry view/change check; history editing and deletion remain forbidden.

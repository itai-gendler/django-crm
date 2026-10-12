---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-record"
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
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email removal permissions

Native removal requires the effective Email delete permission and ordered ownership/department clarification; helper-created drafts do not acquire a native Add requirement.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "resolution",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::memo-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/resolution.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Resolution reading permissions

Reads Memo Resolution through permitted Memo presentation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

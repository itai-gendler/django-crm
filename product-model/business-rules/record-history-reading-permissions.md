---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "history",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::record-history"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Record history reading permissions

Reads selected-subject History; actual model/object history checks.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

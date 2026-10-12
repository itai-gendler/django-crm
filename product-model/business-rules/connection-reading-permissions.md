---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "connection",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::callback"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "voip/models.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Connection reading permissions

Reads callback choices; current User’s active Connections. The route has no staff/login wrapper.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

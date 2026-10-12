---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "department",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::request-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Department reading permissions

Reads Department facts through permitted scope/default/parent controls.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

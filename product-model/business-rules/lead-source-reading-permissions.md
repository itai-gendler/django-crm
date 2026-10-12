---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead-source",
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
      "target": "crm/models/others.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Lead source reading permissions

Reads source configuration in mapped staff controls; public source resolution is input validation, not model authorization.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "crm-tag",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/tag.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Crm tag reading permissions

Reads CRM Tag names/choices through actual host presentation and choice scope.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

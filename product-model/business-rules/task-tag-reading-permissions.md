---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task-tag",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::task-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/tag.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Task tag reading permissions

Reads Task Tag names/choices through actual work presentation and applicability.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

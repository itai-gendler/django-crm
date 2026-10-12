---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "work-stage",
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
      "target": "tasks/models/stagebase.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Task stage reading permissions

Reads work-stage Task choices through permitted Task presentation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

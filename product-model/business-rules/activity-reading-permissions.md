---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "activity-log",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
        },
        {
          "place": "crm-web::crm-workspace::task-record"
        },
        {
          "place": "crm-web::crm-workspace::project-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/taskbase.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Activity reading permissions

Reads subject Activity Log; actual authorized subject presentation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

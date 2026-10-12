---
{
  "kind": "primary",
  "routes": {
    "main": "Edit project"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Project and invoke edit.",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::project-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected work record retains the submitted name, description, note, priority, stage and due date; Active follows the stage, and modifying account/update time are retained.",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Priority",
            "Stage",
            "Due date",
            "Next step",
            "Next step date",
            "Reminder",
            "Updated",
            "Modified by",
            "Active"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::project-record"
        }
      },
      "actor": "co-worker"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ]
}
---

# Edit project

## Trigger

Co worker invokes Edit project.

## Outcome

The selected work record retains the submitted name, description, note, priority, stage and due date; Active follows the stage, and modifying account/update time are retained.

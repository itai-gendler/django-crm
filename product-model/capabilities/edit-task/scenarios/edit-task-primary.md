---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke edit.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected work record retains the submitted name, description, note, priority, stage and due date; Active follows the stage, and modifying account/update time are retained.",
      "entities": [
        {
          "entity": "task",
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
            "Hide main task",
            "Parent task",
            "Project",
            "Updated",
            "Modified by",
            "Active"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "actor": "co-worker"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/taskadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/forms.py"
    }
  ]
}
---

# Edit task

## Trigger

Co worker invokes Edit task.

## Outcome

The selected work record retains the submitted name, description, note, priority, stage and due date; Active follows the stage, and modifying account/update time are retained.

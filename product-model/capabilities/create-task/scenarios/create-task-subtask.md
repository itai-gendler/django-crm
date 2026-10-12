---
{
  "kind": "primary",
  "routes": {
    "main": "Create task — subtask"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The new Task is submitted with a selected parent Task.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [],
          "as": "main-task"
        }
      ],
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save work content, stage, dates and responsible people.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The new Task belongs to its main Task.",
      "entities": [
        {
          "entity": "task",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Priority",
            "Stage",
            "Active",
            "Start date",
            "Due date",
            "Closing date",
            "Next step",
            "Next step date",
            "Reminder",
            "Completion token",
            "Hide main task",
            "Owner",
            "Co-owner",
            "Department",
            "Responsible people",
            "Subscribers",
            "Tags",
            "Parent task",
            "Project",
            "Created",
            "Updated",
            "Modified by"
          ],
          "as": "new-subtask"
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

# Create task — subtask

## Trigger

Co worker invokes Create task.

## Outcome

The new Task belongs to its main Task.

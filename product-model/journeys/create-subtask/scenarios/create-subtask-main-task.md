---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
          "facts": [],
          "as": "main-task"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "capability": "edit-task"
    },
    {
      "kind": "product",
      "text": "The Product presents the selected work and its linked creation control.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Name"
          ],
          "as": "main-task"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "actor": "co-worker",
      "capability": "edit-task"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "edit-task",
      "text": "The selected work creation link opens the prefilled child-work Add form with its source association.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
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
      },
      "capability": "create-task"
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
      "actor": "co-worker",
      "capability": "create-task"
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

# Create subtask — main task

## Trigger

The co worker starts by select Task and invoke edit.

## Outcome

The new Task belongs to its main Task.

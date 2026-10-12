---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task — child closes main"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "No active children remain and done inactive children’s responsible-set union exactly equals the eligible parent’s responsible set. The child also has an attachment not already referenced by its parent.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke edit.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [],
          "as": "child-task"
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
      "text": "The child Task is closed. With no active children and an exact union of done-child responsible people matching the eligible parent, the main Task is also closed and its workflow and closing notice are updated. Unique attachment references are copied to the parent; physical storage is shared.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Stage",
            "Active",
            "Closing date",
            "Next step"
          ],
          "as": "child-task"
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Stage",
            "Active",
            "Closing date",
            "Next step",
            "Next step date"
          ],
          "as": "main-task"
        },
        {
          "entity": "file",
          "as": "parent-attachment",
          "effect": "creates",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/task.py"
    }
  ]
}
---

# Edit task — child closes main

## Trigger

Co worker invokes Edit task.

## Outcome

The child Task is closed. With no active children and an exact union of done-child responsible people matching the eligible parent, the main Task is also closed and its workflow and closing notice are updated. Unique attachment references are copied to the parent without duplicating physical storage.

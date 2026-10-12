---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task — child leaves main open"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "A child Task is closed while another child is active or the parent’s responsible set is unmatched; a unique child attachment is available to copy.",
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
      "text": "The child Task is closed, but unmatched responsible membership or another active child leaves the main Task open. Unique attachment references are copied to the parent; physical storage is shared.",
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
          "effect": "reads",
          "facts": [
            "Stage",
            "Active",
            "Responsible people"
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

# Edit task — child leaves main open

## Trigger

Co worker invokes Edit task.

## Outcome

The child Task is closed, but unmatched responsible membership or another active child leaves the main Task open. Unique attachment references are copied to the parent without duplicating physical storage.

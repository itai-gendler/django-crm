---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task — child reopens main"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The child Task is submitted with an active stage while its parent is inactive.",
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
      "text": "The child Task becomes active; an inactive main Task is moved to the configured in-progress stage. Its earlier closing date is not asserted to be cleared.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Stage",
            "Active"
          ],
          "as": "child-task"
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Stage",
            "Active"
          ],
          "as": "main-task"
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

# Edit task — child reopens main

## Trigger

Co worker invokes Edit task.

## Outcome

The child Task becomes active; an inactive main Task is moved to the configured in-progress stage. Its earlier closing date is not asserted to be cleared.

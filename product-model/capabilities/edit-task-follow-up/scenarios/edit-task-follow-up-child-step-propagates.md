---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task follow up — child step propagates"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The child’s follow-up changes while the parent retains the initial step or a later next-step date.",
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
      "text": "The child Task’s follow-up is saved and copied to the main Task when its prior follow-up is the acquaintance default or its next-step date is later. Both workflows record the actual follow-up.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Next step",
            "Next step date"
          ],
          "as": "child-task"
        },
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Next step",
            "Next step date"
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

# Edit task follow up — child step propagates

## Trigger

Co worker invokes Edit task follow up.

## Outcome

The child Task’s follow-up is saved and copied to the main Task when its prior follow-up is the acquaintance default or its next-step date is later. Both workflows record the actual follow-up.

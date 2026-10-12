---
{
  "kind": "primary",
  "routes": {
    "main": "Add task subscriber"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke add.",
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
      "text": "The selected task subscriber membership is retained on the saved Task. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Subscribers"
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

# Add task subscriber

## Trigger

Co worker invokes Add task subscriber.

## Outcome

The selected task subscriber membership is retained on the saved Task. Other retained memberships are preserved.

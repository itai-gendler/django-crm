---
{
  "kind": "primary",
  "routes": {
    "main": "Add task responsible person"
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
      "text": "The selected task responsible person membership is retained on the saved Task. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Responsible people"
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

# Add task responsible person

## Trigger

Co worker invokes Add task responsible person.

## Outcome

The selected task responsible person membership is retained on the saved Task. Other retained memberships are preserved.

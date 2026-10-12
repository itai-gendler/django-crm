---
{
  "kind": "primary",
  "routes": {
    "main": "Remove task responsible person"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke remove.",
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
      "text": "The selected task responsible person membership is removed from the saved Task. Other retained memberships are preserved.",
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

# Remove task responsible person

## Trigger

Co worker invokes Remove task responsible person.

## Outcome

The selected task responsible person membership is removed from the saved Task. Other retained memberships are preserved.

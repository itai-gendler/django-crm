---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task co owner"
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
      "text": "The selected Task retains the submitted Co-owner. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Co-owner"
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

# Edit task co owner

## Trigger

Co worker invokes Edit task co owner.

## Outcome

The selected Task retains the submitted Co-owner. Read-only fields retain their previous values and invalid form input returns field errors.

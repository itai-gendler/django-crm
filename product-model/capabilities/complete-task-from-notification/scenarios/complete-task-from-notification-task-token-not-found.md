---
{
  "kind": "validation",
  "routes": {
    "main": "Complete task from notification — task token not found"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The notification token resolves no Task.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "task-link-holder"
    },
    {
      "kind": "actor",
      "actor": "task-link-holder",
      "text": "Follow the notification completion link with its token and selected account identifier.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::public::task-completion"
        }
      }
    },
    {
      "kind": "product",
      "text": "Missing Task token returns its not-found response without synthetic posting.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Priority"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::public::task-completion"
        }
      },
      "actor": "task-link-holder"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/task_completed.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/create_completed_subtask.py"
    }
  ]
}
---

# Complete task from notification — task token not found

## Trigger

Task link holder invokes Complete task from notification.

## Outcome

Missing Task token returns its not-found response without synthetic posting.

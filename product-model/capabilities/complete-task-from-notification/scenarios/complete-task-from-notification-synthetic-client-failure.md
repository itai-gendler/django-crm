---
{
  "kind": "edge",
  "routes": {
    "main": "Complete task from notification — synthetic client failure"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The public completion’s internal native request or response assertion fails.",
      "entities": [
        {
          "entity": "request",
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
      "text": "Synthetic-client exception/status failure has no invented graceful success.",
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

# Complete task from notification — synthetic client failure

## Trigger

Task link holder invokes Complete task from notification.

## Outcome

Synthetic-client exception/status failure has no invented graceful success.

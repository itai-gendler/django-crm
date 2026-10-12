---
{
  "kind": "edge",
  "routes": {
    "main": "Complete task from notification — closed notice without confirmed mutation"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The synthetic post returns a status-200 form page without confirmed mutation.",
      "entities": []
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
      "text": "The closed notice can follow a status-200 form page without a confirmed stage mutation.",
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

# Complete task from notification — closed notice without confirmed mutation

## Trigger

Task link holder invokes Complete task from notification.

## Outcome

The closed notice can follow a status-200 form page without a confirmed stage mutation.

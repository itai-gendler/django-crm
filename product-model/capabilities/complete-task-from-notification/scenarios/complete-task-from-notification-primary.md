---
{
  "kind": "primary",
  "routes": {
    "main": "Complete task from notification"
  },
  "steps": [
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
      "text": "On the successful native-save path the Task retains Done, stage-derived Active, closing date and Hide main task. The callback then renders closed; its separate status-200-form case has no confirmed mutation.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Stage",
            "Active",
            "Closing date",
            "Hide main task",
            "Next step"
          ]
        },
        {
          "entity": "user",
          "effect": "reads",
          "facts": []
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

# Complete task from notification

## Trigger

Task link holder invokes Complete task from notification.

## Outcome

On the successful native-save path the Task retains Done, stage-derived Active, closing date and Hide main task. The callback then renders closed; its separate status-200-form case has no confirmed mutation.

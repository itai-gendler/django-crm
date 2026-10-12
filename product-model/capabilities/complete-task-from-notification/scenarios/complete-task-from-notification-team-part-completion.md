---
{
  "kind": "primary",
  "routes": {
    "main": "Complete task from notification — team part completion"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected main Task has multiple responsible people and the participant completes a separate child.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [],
          "as": "main-task"
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
      "text": "After the actual preflight continues and the internal Add form saves, a Done hidden participant subtask is retained. Parent closure occurs only under its exact eligibility, child-state and responsible-set conditions. Workflow attribution uses the internally selected account.",
      "entities": [
        {
          "entity": "task",
          "effect": "creates",
          "as": "completed-part",
          "facts": [
            "Name",
            "Description",
            "Note",
            "Priority",
            "Stage",
            "Active",
            "Start date",
            "Due date",
            "Closing date",
            "Next step",
            "Next step date",
            "Reminder",
            "Completion token",
            "Hide main task",
            "Owner",
            "Co-owner",
            "Department",
            "Responsible people",
            "Subscribers",
            "Tags",
            "Parent task",
            "Project",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "task",
          "effect": "changes",
          "as": "main-task",
          "facts": [
            "Stage",
            "Active",
            "Closing date",
            "Next step",
            "Next step date"
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

# Complete task from notification — team part completion

## Trigger

Task link holder invokes Complete task from notification.

## Outcome

After the actual preflight continues and the internal Add form saves, a Done hidden participant subtask is retained. Parent closure occurs only under its exact eligibility, child-state and responsible-set conditions. Workflow attribution uses the internally selected account.

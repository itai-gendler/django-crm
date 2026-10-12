---
{
  "kind": "primary",
  "routes": {
    "main": "Complete task — team part completion"
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
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke complete.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [],
          "as": "main-task"
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
      "text": "The successful native Add creates a Done hidden participant subtask. If parent eligibility, no-active-child and exact responsible-set conditions hold, the parent closes with Done next step and today's next-step/closing dates. Workflow entries are recorded by Activity recording.",
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
      "target": "tasks/views/create_completed_subtask.py"
    }
  ]
}
---

# Complete task — team part completion

## Trigger

Co worker invokes Complete task.

## Outcome

The successful native Add creates a Done hidden participant subtask. If parent eligibility, no-active-child and exact responsible-set conditions hold, the parent closes with Done next step and today's next-step/closing dates. Workflow entries are recorded by Activity recording.

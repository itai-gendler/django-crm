---
{
  "kind": "primary",
  "routes": {
    "main": "Complete task"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke complete.",
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
      "text": "The whole-task completion save sets the first Done stage, derives Active from stage, sets closing date and Hide main task, and updates the source-defined next step. Its workflow entry is recorded by Activity recording.",
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

# Complete task

## Trigger

Co worker invokes Complete task.

## Outcome

The whole-task completion save sets the first Done stage, derives Active from stage, sets closing date and Hide main task, and updates the source-defined next step. Its workflow entry is recorded by Activity recording.

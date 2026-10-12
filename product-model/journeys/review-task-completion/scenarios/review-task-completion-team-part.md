---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      "capability": "complete-task",
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
      },
      "capability": "complete-task"
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
      "actor": "co-worker",
      "capability": "complete-task"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "complete-task",
      "text": "The Product opens the work browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke browse.",
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
          "place": "crm-web::crm-workspace::task-browser"
        }
      },
      "capability": "browse-tasks"
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Name",
            "Next step",
            "Next step date",
            "Due date",
            "Priority",
            "Stage",
            "Responsible people",
            "Active",
            "Created"
          ],
          "as": "main-task"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-browser"
        }
      },
      "actor": "co-worker",
      "capability": "browse-tasks"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/create_completed_subtask.py"
    },
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

# Review task completion — team part

## Trigger

The co worker starts by select Task and invoke complete.

## Outcome

The participant completes a team part, returns to the work browser and can inspect the source-selected work. The child is distinct; parent closure occurs only under its exact completion conditions.

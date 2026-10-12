---
{
  "kind": "edge",
  "routes": {
    "main": "Edit task follow up — date after due warning"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted next-step date is later than the work’s due date but is not a rejected past date.",
      "entities": []
    },
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
      "text": "The later-than-due next step is saved with a warning.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Next step",
            "Next step date",
            "Reminder"
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

# Edit task follow up — date after due warning

## Trigger

Co worker invokes Edit task follow up.

## Outcome

The later-than-due next step is saved with a warning.

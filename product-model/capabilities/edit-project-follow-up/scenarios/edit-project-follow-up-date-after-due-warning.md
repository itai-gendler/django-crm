---
{
  "kind": "edge",
  "routes": {
    "main": "Edit project follow up — date after due warning"
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
      "text": "Select Project and invoke edit.",
      "entities": [
        {
          "entity": "project",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::project-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The later-than-due next step is saved with a warning.",
      "entities": [
        {
          "entity": "project",
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
          "place": "crm-web::crm-workspace::project-record"
        }
      },
      "actor": "co-worker"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ]
}
---

# Edit project follow up — date after due warning

## Trigger

Co worker invokes Edit project follow up.

## Outcome

The later-than-due next step is saved with a warning.

---
{
  "kind": "primary",
  "routes": {
    "main": "Edit project follow up"
  },
  "steps": [
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
      "text": "Next step/date and reminder facts are saved under the source follow-up field policy.",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Next step",
            "Next step date",
            "Reminder"
          ]
        },
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": []
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

# Edit project follow up

## Trigger

Co worker invokes Edit project follow up.

## Outcome

Next step/date and reminder facts are saved under the source follow-up field policy.

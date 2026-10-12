---
{
  "kind": "validation",
  "routes": {
    "main": "Edit project follow up — past date"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted changed next-step date precedes today.",
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
      "text": "The changed past follow-up date is rejected.",
      "entities": [
        {
          "entity": "project",
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

# Edit project follow up — past date

## Trigger

Co worker invokes Edit project follow up.

## Outcome

The changed past follow-up date is rejected.

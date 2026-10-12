---
{
  "kind": "validation",
  "routes": {
    "main": "Create project — past due date"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted changed due date precedes today.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save work content, dates and responsible people.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::project-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The changed past due date is rejected.",
      "entities": [],
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

# Create project — past due date

## Trigger

Co worker invokes Create project.

## Outcome

The changed past due date is rejected.

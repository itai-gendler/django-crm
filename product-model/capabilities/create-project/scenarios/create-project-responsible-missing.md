---
{
  "kind": "validation",
  "routes": {
    "main": "Create project — responsible missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted work has no responsible people.",
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
      "text": "Missing responsible people are rejected.",
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

# Create project — responsible missing

## Trigger

Co worker invokes Create project.

## Outcome

Missing responsible people are rejected.

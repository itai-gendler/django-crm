---
{
  "kind": "validation",
  "routes": {
    "main": "Create task — subtask multiple responsible"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The new child work input contains more than one responsible person.",
      "entities": [],
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save work content, stage, dates and responsible people.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Multiple responsible people on a subtask are rejected.",
      "entities": [],
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

# Create task — subtask multiple responsible

## Trigger

Co worker invokes Create task.

## Outcome

Multiple responsible people on a subtask are rejected.

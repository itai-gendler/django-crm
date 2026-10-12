---
{
  "kind": "primary",
  "routes": {
    "main": "Browse tasks"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke browse.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-browser"
        }
      }
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
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-browser"
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

# Browse tasks

## Trigger

Co worker invokes Browse tasks.

## Outcome

Present the source-defined Task selection, search/filter results and summary facts.

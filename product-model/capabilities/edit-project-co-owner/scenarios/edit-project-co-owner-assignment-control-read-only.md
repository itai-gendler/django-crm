---
{
  "kind": "validation",
  "routes": {
    "main": "Edit project co owner — assignment control read only"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current editor is neither owner nor co-owner and has neither Task operator nor Superuser status.",
      "entities": [
        {
          "entity": "task-operator",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "operator",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
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
      "text": "Unavailable assignment controls leave membership unchanged.",
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

# Edit project co owner — assignment control read only

## Trigger

Co worker invokes Edit project co owner.

## Outcome

Unavailable assignment controls leave membership unchanged.

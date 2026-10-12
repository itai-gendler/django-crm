---
{
  "kind": "primary",
  "routes": {
    "main": "Edit project co owner"
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
      "text": "The selected Project retains the submitted Co-owner. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Co-owner"
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

# Edit project co owner

## Trigger

Co worker invokes Edit project co owner.

## Outcome

The selected Project retains the submitted Co-owner. Read-only fields retain their previous values and invalid form input returns field errors.

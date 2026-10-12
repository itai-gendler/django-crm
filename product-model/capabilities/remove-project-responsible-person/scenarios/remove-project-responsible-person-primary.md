---
{
  "kind": "primary",
  "routes": {
    "main": "Remove project responsible person"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Project and invoke remove.",
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
      "text": "The selected project responsible person membership is removed from the saved Project. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Responsible people"
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

# Remove project responsible person

## Trigger

Co worker invokes Remove project responsible person.

## Outcome

The selected project responsible person membership is removed from the saved Project. Other retained memberships are preserved.

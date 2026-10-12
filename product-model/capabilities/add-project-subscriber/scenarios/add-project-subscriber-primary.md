---
{
  "kind": "primary",
  "routes": {
    "main": "Add project subscriber"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Project and invoke add.",
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
      "text": "The selected project subscriber membership is retained on the saved Project. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "project",
          "effect": "changes",
          "facts": [
            "Subscribers"
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

# Add project subscriber

## Trigger

Co worker invokes Add project subscriber.

## Outcome

The selected project subscriber membership is retained on the saved Project. Other retained memberships are preserved.

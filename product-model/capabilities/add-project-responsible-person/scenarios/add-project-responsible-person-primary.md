---
{
  "kind": "primary",
  "routes": {
    "main": "Add project responsible person"
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
      "text": "The selected project responsible person membership is retained on the saved Project. Other retained memberships are preserved.",
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

# Add project responsible person

## Trigger

Co worker invokes Add project responsible person.

## Outcome

The selected project responsible person membership is retained on the saved Project. Other retained memberships are preserved.

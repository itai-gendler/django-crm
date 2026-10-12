---
{
  "kind": "validation",
  "routes": {
    "main": "Remove task responsible person — last responsible"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The proposed work assignment removes its final responsible person.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke remove.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Removing the final responsible person is rejected.",
      "entities": [
        {
          "entity": "task",
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

# Remove task responsible person — last responsible

## Trigger

Co worker invokes Remove task responsible person.

## Outcome

Removing the final responsible person is rejected.

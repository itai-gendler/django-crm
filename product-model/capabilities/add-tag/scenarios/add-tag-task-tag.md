---
{
  "kind": "primary",
  "routes": {
    "main": "Add tag — task tag"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected tag is a Task Tag attached to work.",
      "entities": [
        {
          "entity": "task-tag",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Task and invoke add.",
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
      "text": "The selected Task’s work-tag membership changes.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Tags"
          ]
        },
        {
          "entity": "task-tag",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    }
  ]
}
---

# Add tag — task tag

## Trigger

Operator invokes Add tag.

## Outcome

The selected Task’s work-tag membership changes.

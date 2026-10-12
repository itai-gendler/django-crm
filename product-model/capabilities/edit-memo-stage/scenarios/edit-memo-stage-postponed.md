---
{
  "kind": "primary",
  "routes": {
    "main": "Edit memo stage — postponed"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Memo’s processing stage is submitted as Postponed.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "task-operator"
    },
    {
      "kind": "actor",
      "actor": "task-operator",
      "text": "Select Memo and invoke edit.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The processing stage becomes postponed.",
      "entities": [
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Stage",
            "Review date"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      },
      "actor": "task-operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    }
  ]
}
---

# Edit memo stage — postponed

## Trigger

Task operator invokes Edit memo stage.

## Outcome

The processing stage becomes postponed.

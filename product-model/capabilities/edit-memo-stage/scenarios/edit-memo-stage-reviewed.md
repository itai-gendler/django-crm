---
{
  "kind": "primary",
  "routes": {
    "main": "Edit memo stage — reviewed"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Memo’s processing stage is submitted as Reviewed.",
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
      "text": "Reviewed stage/date are retained and the review notice is emitted.",
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

# Edit memo stage — reviewed

## Trigger

Task operator invokes Edit memo stage.

## Outcome

Reviewed stage/date are retained and the review notice is emitted.

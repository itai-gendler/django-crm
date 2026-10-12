---
{
  "kind": "primary",
  "routes": {
    "main": "Edit memo stage"
  },
  "steps": [
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
      "text": "The selected Memo retains the submitted Stage, Review date. Read-only fields retain their previous values and invalid form input returns field errors.",
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

# Edit memo stage

## Trigger

Task operator invokes Edit memo stage.

## Outcome

The selected Memo retains the submitted Stage, Review date. Read-only fields retain their previous values and invalid form input returns field errors.

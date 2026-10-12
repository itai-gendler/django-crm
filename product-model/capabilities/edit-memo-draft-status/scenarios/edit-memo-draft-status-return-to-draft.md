---
{
  "kind": "primary",
  "routes": {
    "main": "Edit memo draft status — return to draft"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The existing Memo owner sets Draft on the ordinary owner fieldset.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
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
      "text": "The owner’s draft edit follows the source notification suppression branch.",
      "entities": [
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Draft",
            "Notified"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      },
      "actor": "co-worker"
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

# Edit memo draft status — return to draft

## Trigger

Co worker invokes Edit memo draft status.

## Outcome

The owner’s draft edit follows the source notification suppression branch.

---
{
  "kind": "validation",
  "routes": {
    "main": "Edit memo — reviewed owner read only"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Memo is Reviewed and the current owner has none of the privileged work-role overrides.",
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
      "text": "The reviewed owner’s ordinary change is refused.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Conclusion",
            "Owner"
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

# Edit memo — reviewed owner read only

## Trigger

Co worker invokes Edit memo.

## Outcome

The reviewed owner’s ordinary change is refused.

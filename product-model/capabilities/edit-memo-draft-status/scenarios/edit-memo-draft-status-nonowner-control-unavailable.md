---
{
  "kind": "validation",
  "routes": {
    "main": "Edit memo draft status — nonowner control unavailable"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current account is not the Memo owner and has no ordinary Draft input.",
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
      "text": "The owner-only draft control leaves draft unchanged.",
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

# Edit memo draft status — nonowner control unavailable

## Trigger

Co worker invokes Edit memo draft status.

## Outcome

The owner-only draft control leaves draft unchanged.

---
{
  "kind": "primary",
  "routes": {
    "main": "Remove memo subscriber"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Memo and invoke remove.",
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
      "text": "The selected memo subscriber membership is removed from the saved Memo. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Subscribers"
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

# Remove memo subscriber

## Trigger

Co worker invokes Remove memo subscriber.

## Outcome

The selected memo subscriber membership is removed from the saved Memo. Other retained memberships are preserved.

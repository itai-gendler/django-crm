---
{
  "kind": "primary",
  "routes": {
    "main": "Add memo subscriber"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Memo and invoke add.",
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
      "text": "The selected memo subscriber membership is retained on the saved Memo. Other retained memberships are preserved.",
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

# Add memo subscriber

## Trigger

Co worker invokes Add memo subscriber.

## Outcome

The selected memo subscriber membership is retained on the saved Memo. Other retained memberships are preserved.

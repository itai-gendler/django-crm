---
{
  "kind": "primary",
  "routes": {
    "main": "Edit memo draft status"
  },
  "steps": [
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
      "text": "The selected Memo retains the submitted Draft, Notified. Read-only fields retain their previous values and invalid form input returns field errors.",
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

# Edit memo draft status

## Trigger

Co worker invokes Edit memo draft status.

## Outcome

The selected Memo retains the submitted Draft, Notified. Read-only fields retain their previous values and invalid form input returns field errors.

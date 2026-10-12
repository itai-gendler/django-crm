---
{
  "kind": "primary",
  "routes": {
    "main": "Delete memo"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Memo and invoke delete.",
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
      "text": "Remove the selected Memo.",
      "entities": [
        {
          "entity": "memo",
          "effect": "removes"
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

# Delete memo

## Trigger

Co worker invokes Delete memo.

## Outcome

Remove the selected Memo.

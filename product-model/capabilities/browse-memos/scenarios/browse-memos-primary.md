---
{
  "kind": "primary",
  "routes": {
    "main": "Browse memos"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Memo and invoke browse.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Present the source-defined Memo selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Conclusion",
            "Owner",
            "Recipient",
            "Department",
            "Draft",
            "Notified"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-browser"
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

# Browse memos

## Trigger

Co worker invokes Browse memos.

## Outcome

Present the source-defined Memo selection, search/filter results and summary facts.

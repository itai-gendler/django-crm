---
{
  "kind": "primary",
  "routes": {
    "main": "Create memo"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save the office communication, addressee, conclusion and draft choice.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Memo is retained with Name, Description, Conclusion, Recipient, Draft. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "memo",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Conclusion",
            "Owner",
            "Recipient",
            "Department",
            "Draft",
            "Notified",
            "Stage",
            "Resolution",
            "Review date",
            "Deal",
            "Task",
            "Project",
            "Subscribers",
            "Tags",
            "Created",
            "Updated",
            "Modified by"
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

# Create memo

## Trigger

Co worker invokes Create memo.

## Outcome

A distinct Memo is retained with Name, Description, Conclusion, Recipient, Draft. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

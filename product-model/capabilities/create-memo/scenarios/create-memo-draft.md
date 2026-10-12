---
{
  "kind": "primary",
  "routes": {
    "main": "Create memo — draft"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The new office communication is submitted as a draft.",
      "entities": [],
      "actor": "co-worker"
    },
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
      "text": "The draft is retained without initial recipient notification.",
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

# Create memo — draft

## Trigger

Co worker invokes Create memo.

## Outcome

The draft is retained without initial recipient notification.

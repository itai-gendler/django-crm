---
{
  "kind": "primary",
  "routes": {
    "main": "Create memo — copy memo"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The new Memo form is prefilled from the selected existing Memo.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": [],
          "as": "source-memo"
        }
      ],
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
      "text": "Copied form values create a distinct Memo.",
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
          ],
          "as": "copied-memo"
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

# Create memo — copy memo

## Trigger

Co worker invokes Create memo.

## Outcome

Copied form values create a distinct Memo.

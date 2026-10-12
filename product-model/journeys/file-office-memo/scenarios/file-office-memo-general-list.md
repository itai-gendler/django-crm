---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      },
      "capability": "create-memo"
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
      "actor": "co-worker",
      "capability": "create-memo"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "create-memo",
      "text": "The Product opens the office-communication browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::memo-record"
        }
      }
    },
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
      },
      "capability": "browse-memos"
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
      "actor": "co-worker",
      "capability": "browse-memos"
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

# File office memo — general list

## Trigger

The co worker starts by save the office communication, addressee, conclusion and draft choice.

## Outcome

The author saves a new Memo and reaches the general or Deal-filtered office-communication browser, where the corresponding record is presented.

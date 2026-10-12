---
{
  "kind": "primary",
  "routes": {
    "main": "Edit memo"
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
      "text": "The selected Memo retains the submitted Name, Description, Conclusion, Recipient, Resolution, Deal, Task, Project. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "memo",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Conclusion",
            "Recipient",
            "Resolution",
            "Deal",
            "Task",
            "Project"
          ]
        },
        {
          "entity": "project",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "resolution",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
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

# Edit memo

## Trigger

Co worker invokes Edit memo.

## Outcome

The selected Memo retains the submitted Name, Description, Conclusion, Recipient, Resolution, Deal, Task, Project. Read-only fields retain their previous values and invalid form input returns field errors.

---
{
  "kind": "validation",
  "routes": {
    "main": "Edit memo stage — stage control unavailable"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current editor is an ordinary Memo owner without Chief, Task operator or Superuser status.",
      "entities": [
        {
          "entity": "task-operator",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "operator",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "memo",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
    },
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
      "text": "The processing stage remains unchanged.",
      "entities": [
        {
          "entity": "memo",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Conclusion",
            "Owner"
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

# Edit memo stage — stage control unavailable

## Trigger

Co worker submits the stated case.

## Outcome

The processing stage remains unchanged.

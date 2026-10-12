---
{
  "kind": "edge",
  "routes": {
    "main": "Export tasks — output missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The export download is requested but its generated workbook file is absent.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "file",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke export.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The missing workbook returns a not-found response.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": [
            "Name",
            "Next step",
            "Next step date",
            "Due date",
            "Priority",
            "Stage",
            "Responsible people",
            "Active",
            "Created"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-browser"
        }
      },
      "actor": "co-worker"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/views/export_objects.py"
    }
  ]
}
---

# Export tasks — output missing

## Trigger

Co worker invokes Export tasks.

## Outcome

The missing workbook returns a not-found response.

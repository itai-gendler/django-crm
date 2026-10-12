---
{
  "kind": "primary",
  "routes": {
    "main": "Export tasks"
  },
  "steps": [
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
      "text": "Produce the workbook projection of the selected Task records.",
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

# Export tasks

## Trigger

Co worker invokes Export tasks.

## Outcome

Produce the workbook projection of the selected Task records.

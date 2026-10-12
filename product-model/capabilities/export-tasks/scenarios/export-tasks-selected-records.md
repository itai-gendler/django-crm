---
{
  "kind": "primary",
  "routes": {
    "main": "Export tasks — selected records"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The native export action passes its selected queryset rather than the whole download endpoint selection.",
      "entities": []
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
      "text": "The workbook represents the passed selected queryset.",
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

# Export tasks — selected records

## Trigger

Co worker invokes Export tasks.

## Outcome

The workbook represents the passed selected queryset.

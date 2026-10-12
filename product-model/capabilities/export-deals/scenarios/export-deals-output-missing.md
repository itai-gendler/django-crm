---
{
  "kind": "edge",
  "routes": {
    "main": "Export deals — output missing"
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
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke export.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The missing workbook returns a not-found response.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name",
            "Important",
            "Active",
            "Relevant",
            "Next step",
            "Next step date",
            "Stage",
            "Company",
            "Contact person",
            "Lead"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-browser"
        }
      },
      "actor": "operator"
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

# Export deals — output missing

## Trigger

Operator invokes Export deals.

## Outcome

The missing workbook returns a not-found response.

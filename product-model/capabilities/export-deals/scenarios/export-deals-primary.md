---
{
  "kind": "primary",
  "routes": {
    "main": "Export deals"
  },
  "steps": [
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
      "text": "Produce the workbook projection of the selected Deal records.",
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

# Export deals

## Trigger

Operator invokes Export deals.

## Outcome

Produce the workbook projection of the selected Deal records.

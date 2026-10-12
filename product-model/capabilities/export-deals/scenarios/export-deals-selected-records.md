---
{
  "kind": "primary",
  "routes": {
    "main": "Export deals — selected records"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The native export action passes its selected queryset rather than the whole download endpoint selection.",
      "entities": []
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
      "text": "The workbook represents the passed selected queryset.",
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

# Export deals — selected records

## Trigger

Operator invokes Export deals.

## Outcome

The workbook represents the passed selected queryset.

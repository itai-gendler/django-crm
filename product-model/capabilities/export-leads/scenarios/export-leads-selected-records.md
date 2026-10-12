---
{
  "kind": "primary",
  "routes": {
    "main": "Export leads — selected records"
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
      "text": "Select Lead and invoke export.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The workbook represents the passed selected queryset.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Email address",
            "Company name",
            "Owner",
            "Mailing eligibility",
            "Created"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-browser"
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

# Export leads — selected records

## Trigger

Operator invokes Export leads.

## Outcome

The workbook represents the passed selected queryset.

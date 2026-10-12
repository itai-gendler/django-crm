---
{
  "kind": "primary",
  "routes": {
    "main": "Export companies — selected records"
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
      "text": "Select Company and invoke export.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The workbook represents the passed selected queryset.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [
            "Full name",
            "Client types",
            "Created",
            "Owner",
            "Mailing eligibility",
            "Registration number"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
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

# Export companies — selected records

## Trigger

Operator invokes Export companies.

## Outcome

The workbook represents the passed selected queryset.

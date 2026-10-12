---
{
  "kind": "primary",
  "routes": {
    "main": "Export companies"
  },
  "steps": [
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
      "text": "Produce the workbook projection of the selected Company records.",
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

# Export companies

## Trigger

Operator invokes Export companies.

## Outcome

Produce the workbook projection of the selected Company records.

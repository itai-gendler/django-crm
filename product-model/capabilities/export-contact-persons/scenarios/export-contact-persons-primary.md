---
{
  "kind": "primary",
  "routes": {
    "main": "Export contact persons"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Contact person and invoke export.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Produce the workbook projection of the selected Contact person records.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Email address",
            "Telephone",
            "Company",
            "Mailing eligibility",
            "Created",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
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

# Export contact persons

## Trigger

Operator invokes Export contact persons.

## Outcome

Produce the workbook projection of the selected Contact person records.

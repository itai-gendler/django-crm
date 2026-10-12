---
{
  "kind": "primary",
  "routes": {
    "main": "Export contact persons — selected records"
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
      "text": "The workbook represents the passed selected queryset.",
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

# Export contact persons — selected records

## Trigger

Operator invokes Export contact persons.

## Outcome

The workbook represents the passed selected queryset.

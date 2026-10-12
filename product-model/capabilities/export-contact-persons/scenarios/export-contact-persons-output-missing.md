---
{
  "kind": "edge",
  "routes": {
    "main": "Export contact persons — output missing"
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
      "text": "The missing workbook returns a not-found response.",
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

# Export contact persons — output missing

## Trigger

Operator invokes Export contact persons.

## Outcome

The missing workbook returns a not-found response.

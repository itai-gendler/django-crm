---
{
  "kind": "edge",
  "routes": {
    "main": "Export leads — output missing"
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
      "text": "The missing workbook returns a not-found response.",
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

# Export leads — output missing

## Trigger

Operator invokes Export leads.

## Outcome

The missing workbook returns a not-found response.

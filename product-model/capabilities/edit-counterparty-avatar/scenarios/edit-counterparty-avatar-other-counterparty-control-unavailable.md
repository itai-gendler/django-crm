---
{
  "kind": "validation",
  "routes": {
    "main": "Edit counterparty avatar — other counterparty control unavailable"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Lead belongs to another account and the editor is not a Superuser.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Lead and invoke edit.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The unavailable avatar control leaves the image unchanged.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Avatar"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/lead.py"
    }
  ]
}
---

# Edit counterparty avatar — other counterparty control unavailable

## Trigger

Operator invokes Edit counterparty avatar.

## Outcome

The unavailable avatar control leaves the image unchanged.

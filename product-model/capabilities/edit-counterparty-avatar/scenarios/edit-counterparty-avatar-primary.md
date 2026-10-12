---
{
  "kind": "primary",
  "routes": {
    "main": "Edit counterparty avatar"
  },
  "steps": [
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
      "text": "The selected Lead retains the submitted Avatar. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
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

# Edit counterparty avatar

## Trigger

Operator invokes Edit counterparty avatar.

## Outcome

The selected Lead retains the submitted Avatar. Read-only fields retain their previous values and invalid form input returns field errors.

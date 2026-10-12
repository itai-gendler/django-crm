---
{
  "kind": "primary",
  "routes": {
    "main": "Specify vip recipients — lead"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparty is a Lead.",
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
      "text": "Choose the eligible audience for main-account routing.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Specify vip recipients. This way uses Lead.",
      "entities": [
        {
          "entity": "newsletter-recipient",
          "effect": "changes",
          "facts": [
            "Routing registration",
            "Routing account",
            "Unsubscribe token"
          ],
          "to": "Registered",
          "from": "Unregistered"
        },
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
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
      "target": "massmail/views/unsubscribes.py"
    }
  ]
}
---

# Specify vip recipients — lead

## Trigger

Operator invokes Specify vip recipients.

## Outcome

Specify vip recipients. This way uses Lead.

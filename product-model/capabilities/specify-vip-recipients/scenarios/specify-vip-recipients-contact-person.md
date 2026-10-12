---
{
  "kind": "primary",
  "routes": {
    "main": "Specify vip recipients — contact person"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparty is a Contact person.",
      "entities": [
        {
          "entity": "contact-person",
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
      "text": "Specify vip recipients. This way uses Contact person.",
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
          "entity": "contact-person",
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

# Specify vip recipients — contact person

## Trigger

Operator invokes Specify vip recipients.

## Outcome

Specify vip recipients. This way uses Contact person.

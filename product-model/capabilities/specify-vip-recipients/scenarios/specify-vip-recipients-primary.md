---
{
  "kind": "primary",
  "routes": {
    "main": "Specify vip recipients"
  },
  "steps": [
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
      "text": "The selected common-owner counterparties receive mailing registrations routed through that owner’s main account.",
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

# Specify vip recipients

## Trigger

Operator invokes Specify vip recipients.

## Outcome

The selected common-owner counterparties receive mailing registrations routed through that owner’s main account.

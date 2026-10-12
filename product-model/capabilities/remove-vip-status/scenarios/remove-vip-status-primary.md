---
{
  "kind": "primary",
  "routes": {
    "main": "Remove vip status"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Newsletter recipient and invoke remove.",
      "entities": [
        {
          "entity": "newsletter-recipient",
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
      "text": "The selected mailing registration, routing account and token are removed; counterparty mailing eligibility is not silently changed.",
      "entities": [
        {
          "entity": "newsletter-recipient",
          "effect": "changes",
          "facts": [
            "Routing registration",
            "Routing account",
            "Unsubscribe token"
          ],
          "to": "Unregistered",
          "from": "Registered"
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

# Remove vip status

## Trigger

Operator invokes Remove vip status.

## Outcome

The selected mailing registration, routing account and token are removed; counterparty mailing eligibility is not silently changed.

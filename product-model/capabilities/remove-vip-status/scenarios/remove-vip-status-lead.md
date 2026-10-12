---
{
  "kind": "primary",
  "routes": {
    "main": "Remove vip status — lead"
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
      "text": "Delete mailing routing registration and token information without merely toggling counterparty mailing eligibility. This way uses Lead.",
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

# Remove vip status — lead

## Trigger

Operator invokes Remove vip status.

## Outcome

Delete mailing routing registration and token information without merely toggling counterparty mailing eligibility. This way uses Lead.

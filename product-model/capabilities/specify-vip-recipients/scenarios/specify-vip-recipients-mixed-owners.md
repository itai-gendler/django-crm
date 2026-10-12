---
{
  "kind": "validation",
  "routes": {
    "main": "Specify vip recipients — mixed owners"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparties belong to different owners.",
      "entities": []
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
      "text": "The mixed-owner selection is rejected.",
      "entities": [
        {
          "entity": "newsletter-recipient",
          "effect": "reads",
          "facts": [
            "Identity",
            "Subject",
            "Routing registration",
            "Routing account"
          ]
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

# Specify vip recipients — mixed owners

## Trigger

Operator invokes Specify vip recipients.

## Outcome

The mixed-owner selection is rejected.

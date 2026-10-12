---
{
  "kind": "edge",
  "routes": {
    "main": "Specify vip recipients — main account missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The account whose main email account is needed by this operation has none.",
      "entities": [
        {
          "entity": "email-account",
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
      "text": "Missing main account is reported without establishing the intended draft/routing.",
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

# Specify vip recipients — main account missing

## Trigger

Operator invokes Specify vip recipients.

## Outcome

Missing main account is reported without establishing the intended draft/routing.

---
{
  "kind": "primary",
  "routes": {
    "main": "Unsubscribe"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "newsletter-recipient",
      "text": "Follow the registration’s unsubscribe link.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::public"
        }
      }
    },
    {
      "kind": "product",
      "text": "Resolve the registration token and disable its and its linked counterparty’s mailing eligibility. Unknown tokens redirect without mutation.",
      "entities": [
        {
          "entity": "newsletter-recipient",
          "effect": "changes",
          "facts": [
            "Mailing eligibility"
          ]
        },
        {
          "entity": "company",
          "effect": "changes",
          "facts": [
            "Mailing eligibility"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::public"
        }
      },
      "actor": "newsletter-recipient"
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

# Unsubscribe

## Trigger

Newsletter recipient invokes Unsubscribe.

## Outcome

Resolve the registration token and disable its and its linked counterparty’s mailing eligibility. Unknown tokens redirect without mutation.

---
{
  "kind": "primary",
  "routes": {
    "main": "Unsubscribe — already unsubscribed"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The supplied token resolves an existing registration whose mailing eligibility is already false.",
      "entities": []
    },
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
      "text": "The known registration remains ineligible and redirects.",
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

# Unsubscribe — already unsubscribed

## Trigger

Newsletter recipient invokes Unsubscribe.

## Outcome

The known registration remains ineligible and redirects.

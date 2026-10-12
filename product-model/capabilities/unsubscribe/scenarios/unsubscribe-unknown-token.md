---
{
  "kind": "validation",
  "routes": {
    "main": "Unsubscribe — unknown token"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The supplied unsubscribe token resolves no retained registration.",
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
      "text": "Unknown unsubscribe token redirects without eligibility mutation.",
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

# Unsubscribe — unknown token

## Trigger

Newsletter recipient invokes Unsubscribe.

## Outcome

Unknown unsubscribe token redirects without eligibility mutation.

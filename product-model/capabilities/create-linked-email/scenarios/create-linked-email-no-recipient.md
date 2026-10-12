---
{
  "kind": "edge",
  "routes": {
    "main": "Create linked Email — no recipient"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Deal recipient relationship is empty.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Compose correspondence for the linked commercial subject.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The missing selected Deal recipient is reported and the helper redirects without creating correspondence.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Partner contact",
            "Contact person",
            "Lead",
            "Company"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/create_email.py"
    }
  ]
}
---

# Create linked Email — no recipient

## Trigger

Operator invokes Create linked Email.

## Outcome

The missing selected Deal recipient is reported and the helper redirects without creating correspondence.

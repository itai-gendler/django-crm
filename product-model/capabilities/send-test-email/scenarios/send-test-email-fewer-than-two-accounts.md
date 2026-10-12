---
{
  "kind": "validation",
  "routes": {
    "main": "Send test Email — fewer than two accounts"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Fewer than two eligible email accounts are available for the reusable-content test.",
      "entities": [
        {
          "entity": "email-account",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Email Message and invoke send.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The test-send prerequisite is reported and no multi-account test occurs.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Signature",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-record"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/emlmessageadmin.py"
    }
  ]
}
---

# Send test Email — fewer than two accounts

## Trigger

Sales manager invokes Send test Email.

## Outcome

The test-send prerequisite is reported and no multi-account test occurs.

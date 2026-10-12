---
{
  "kind": "edge",
  "routes": {
    "main": "Send test Email — recipient refused with success notice"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The reusable-content test raises recipient refusal in the handler’s caught branch.",
      "entities": []
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
      "text": "Recipient refusal may produce an error followed by success notice; delivery is not implied.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Signature",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
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

# Send test Email — recipient refused with success notice

## Trigger

Sales manager invokes Send test Email.

## Outcome

Recipient refusal may produce an error followed by success notice; delivery is not implied.

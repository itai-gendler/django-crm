---
{
  "kind": "primary",
  "routes": {
    "main": "Send test Email"
  },
  "steps": [
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
      "text": "The first eligible account sends the selected reusable content to the other eligible account addresses; the handler reports the test outcome.",
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

# Send test Email

## Trigger

Sales manager invokes Send test Email.

## Outcome

The first eligible account sends the selected reusable content to the other eligible account addresses; the handler reports the test outcome.

---
{
  "kind": "primary",
  "routes": {
    "main": "Delete Email message"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Email Message and invoke delete.",
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
      "text": "Remove the selected Email Message.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "removes"
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

# Delete Email message

## Trigger

Sales manager invokes Delete Email message.

## Outcome

Remove the selected Email Message.

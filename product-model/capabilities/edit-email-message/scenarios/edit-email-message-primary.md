---
{
  "kind": "primary",
  "routes": {
    "main": "Edit Email message"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Email Message and invoke edit.",
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
      "text": "The selected Email Message retains the submitted Subject, Content, Signature. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content",
            "Signature",
            "Department"
          ]
        },
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
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

# Edit Email message

## Trigger

Sales manager invokes Edit Email message.

## Outcome

The selected Email Message retains the submitted Subject, Content, Signature. Read-only fields retain their previous values and invalid form input returns field errors.

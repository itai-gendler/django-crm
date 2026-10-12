---
{
  "kind": "primary",
  "routes": {
    "main": "Create Email message"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Save reusable subject, body and signing content choice.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Email Message is retained with Subject, Content, Signature. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "creates",
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

# Create Email message

## Trigger

Sales manager invokes Create Email message.

## Outcome

A distinct Email Message is retained with Subject, Content, Signature. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

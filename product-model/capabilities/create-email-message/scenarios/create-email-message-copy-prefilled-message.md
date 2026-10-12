---
{
  "kind": "primary",
  "routes": {
    "main": "Create Email message — copy prefilled message"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The reusable-content Add form is prefilled from an existing Email Message; the copy is not saved yet.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": [],
          "as": "source-content"
        }
      ],
      "actor": "sales-manager"
    },
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
      "text": "Source values prefill unsaved native Add and are saved as a distinct reusable message.",
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
          ],
          "as": "copied-content"
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

# Create Email message — copy prefilled message

## Trigger

Sales manager invokes Create Email message.

## Outcome

Source values prefill unsaved native Add and are saved as a distinct reusable message.

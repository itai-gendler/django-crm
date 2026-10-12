---
{
  "kind": "primary",
  "routes": {
    "main": "Create linked Email — deal files saved draft"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Deal has files and the actor submits an attachment selection for its correspondence.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "file",
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
      "text": "Selected Deal file references belong to the saved draft opened in its editor.",
      "entities": [
        {
          "entity": "email",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To",
            "CC",
            "BCC",
            "Signature",
            "Date",
            "Ticket",
            "Message identity",
            "Mailbox UID",
            "Email account",
            "Incoming",
            "Sent",
            "Trash",
            "Company",
            "Contact person",
            "Lead",
            "Deal",
            "Request",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "file",
          "effect": "creates",
          "with": "email",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ]
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
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

# Create linked Email — deal files saved draft

## Trigger

Operator invokes Create linked Email.

## Outcome

Selected Deal file references belong to the saved draft opened in its editor.

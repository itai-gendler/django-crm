---
{
  "kind": "primary",
  "routes": {
    "main": "Forward Email"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke forward.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [],
          "as": "source-correspondence"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct saved forward draft carries the source subject, quoted correspondence, ticket, counterparty links and copies of attachment references. The actor enters the new Email in CRM editor.",
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
          ],
          "as": "draft-correspondence"
        },
        {
          "entity": "file",
          "effect": "creates",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ],
          "with": "draft-correspondence"
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
      "target": "crm/views/reply_email.py"
    }
  ]
}
---

# Forward Email

## Trigger

Operator invokes Forward Email.

## Outcome

A distinct saved forward draft carries the source subject, quoted correspondence, ticket, counterparty links and copies of attachment references. The actor enters the new Email in CRM editor.

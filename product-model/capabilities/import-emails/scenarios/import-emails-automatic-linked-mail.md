---
{
  "kind": "primary",
  "routes": {
    "main": "Import Emails — automatic linked mail"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The configured linked-mail queue contains a message for the automatic consumer.",
      "entities": [],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The unattended queue consumer retains supported linked correspondence.",
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
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-browser"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/views/select_emails_import.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/import_emails.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/restore_imap_emails.py"
    }
  ]
}
---

# Import Emails — automatic linked mail

## Trigger

The configured processing condition occurs.

## Outcome

The unattended queue consumer retains supported linked correspondence.

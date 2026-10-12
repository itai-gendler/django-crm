---
{
  "kind": "primary",
  "routes": {
    "main": "Import Emails — ticket linked"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The imported message’s ticket identifies an existing Request or Deal.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the workbook or remote-message selection for processing.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-import"
        }
      }
    },
    {
      "kind": "product",
      "text": "Imported correspondence links to the matching ticket’s Request/Deal.",
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
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-import"
        }
      },
      "actor": "operator"
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

# Import Emails — ticket linked

## Trigger

Operator invokes Import Emails.

## Outcome

Imported correspondence links to the matching ticket’s Request/Deal.

---
{
  "kind": "edge",
  "routes": {
    "main": "Import Emails — imap error"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The remote mailbox operation raises the error handled by the import path.",
      "entities": []
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
      "text": "The remote-header/import error is reported without a completed-import guarantee.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To"
          ]
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

# Import Emails — imap error

## Trigger

Operator invokes Import Emails.

## Outcome

The remote-header/import error is reported without a completed-import guarantee.

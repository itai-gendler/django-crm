---
{
  "kind": "edge",
  "routes": {
    "main": "Import Emails — crm origin skipped"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The remote message has the CRM-origin marker tested by the import path.",
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
      "text": "The CRM-origin message is not imported as another inquiry.",
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

# Import Emails — crm origin skipped

## Trigger

Operator invokes Import Emails.

## Outcome

The CRM-origin message is not imported as another inquiry.

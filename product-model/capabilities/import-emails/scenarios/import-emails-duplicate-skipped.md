---
{
  "kind": "edge",
  "routes": {
    "main": "Import Emails — duplicate skipped"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The import candidate matches the subject-specific duplicate key of an existing saved record.",
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
      "text": "The existing duplicate-key record is retained and another imported record is not added.",
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

# Import Emails — duplicate skipped

## Trigger

Operator invokes Import Emails.

## Outcome

The existing duplicate-key record is retained and another imported record is not added.

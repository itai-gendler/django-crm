---
{
  "kind": "primary",
  "routes": {
    "main": "Download original Email"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Invoke the offered download control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The original saved correspondence is fetched from the selected mailbox and returned as an EML download.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
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
            "Company",
            "Contact person",
            "Lead",
            "Deal",
            "Request",
            "Department"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Download original Email

## Trigger

Operator invokes Download original Email.

## Outcome

The original saved correspondence is fetched from the selected mailbox and returned as an EML download.

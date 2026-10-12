---
{
  "kind": "primary",
  "routes": {
    "main": "Create Email"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save correspondence addresses, subject, body and signing content choice.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Email in CRM is retained with Subject, Content, Sender, To, CC. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
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

# Create Email

## Trigger

Operator invokes Create Email.

## Outcome

A distinct Email in CRM is retained with Subject, Content, Sender, To, CC. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

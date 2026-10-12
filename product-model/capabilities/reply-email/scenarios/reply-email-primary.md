---
{
  "kind": "primary",
  "routes": {
    "main": "Reply Email"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke reply.",
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
      "text": "A distinct saved reply draft carries the source subject, correspondence and reply address, and the actor enters its editor.",
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

# Reply Email

## Trigger

Operator invokes Reply Email.

## Outcome

A distinct saved reply draft carries the source subject, correspondence and reply address, and the actor enters its editor.

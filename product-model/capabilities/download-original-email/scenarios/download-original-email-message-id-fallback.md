---
{
  "kind": "primary",
  "routes": {
    "main": "Download original Email — message id fallback"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The original download identifies the remote correspondence through Message-ID when using its fallback path.",
      "entities": []
    },
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
      "text": "Original download uses Message-ID fallback.",
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

# Download original Email — message id fallback

## Trigger

Operator invokes Download original Email.

## Outcome

Original download uses Message-ID fallback.

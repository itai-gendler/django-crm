---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke send.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "capability": "send-email"
    },
    {
      "kind": "product",
      "text": "SMTP processing returns normally through the correspondence owner's main account. Sent is persisted and the Email browser opens. This records accepted processing, not recipient delivery.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Sent"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator",
      "capability": "send-email"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "send-email",
      "text": "The Product opens the emails in crm browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke browse.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-browser"
        }
      },
      "capability": "browse-emails-in-crm"
    },
    {
      "kind": "product",
      "text": "Present the source-defined Email in CRM selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To",
            "CC",
            "BCC",
            "Signature",
            "Date"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-browser"
        }
      },
      "actor": "operator",
      "capability": "browse-emails-in-crm"
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

# Inspect sent email — accepted send

## Trigger

The operator starts by select Email in CRM and invoke send.

## Outcome

The operator submits Send and, after normal processing saves Sent, reaches the correspondence browser and inspects its displayed status.

---
{
  "kind": "primary",
  "routes": {
    "main": "Send Email"
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
      }
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

# Send Email

## Trigger

Operator invokes Send Email.

## Outcome

SMTP processing returns normally through the Email owner's main account. The linked Deal receives its workflow entry when present, Sent is persisted and the Email browser opens. This records accepted processing, not recipient delivery.

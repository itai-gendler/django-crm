---
{
  "kind": "validation",
  "routes": {
    "main": "Edit Email — incoming or uid read only"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The correspondence is Incoming or has a mailbox UID, the inherited change result is true, and the Manager fallback is not the selected branch.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke edit.",
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
      "text": "The incoming/UID refusing branch leaves correspondence unchanged.",
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

# Edit Email — incoming or uid read only

## Trigger

Operator invokes Edit Email.

## Outcome

The incoming/UID refusing branch leaves correspondence unchanged.

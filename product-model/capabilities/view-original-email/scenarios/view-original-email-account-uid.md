---
{
  "kind": "primary",
  "routes": {
    "main": "View original Email — account uid"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The correspondence retains a mailbox account and UID identifying its remote original.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke view.",
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
      "text": "Stored account/UID identifies the original message, with source UID repair where performed.",
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

# View original Email — account uid

## Trigger

Operator invokes View original Email.

## Outcome

Stored account/UID identifies the original message, with source UID repair where performed.

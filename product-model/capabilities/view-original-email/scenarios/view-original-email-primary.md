---
{
  "kind": "primary",
  "routes": {
    "main": "View original Email"
  },
  "steps": [
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
      "text": "The selected mailbox message’s headers, body and attachments are presented; viewing the original does not rewrite its saved CRM correspondence.",
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

# View original Email

## Trigger

Operator invokes View original Email.

## Outcome

The selected mailbox message’s headers, body and attachments are presented; viewing the original does not rewrite its saved CRM correspondence.

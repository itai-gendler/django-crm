---
{
  "kind": "edge",
  "routes": {
    "main": "View original Email — unidentifiable or fetch error"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The original message cannot be identified in a usable mailbox or its fetch fails.",
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
      "text": "Original identification/fetch failure is returned without invented content.",
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

# View original Email — unidentifiable or fetch error

## Trigger

Operator invokes View original Email.

## Outcome

Original identification/fetch failure is returned without invented content.

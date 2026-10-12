---
{
  "kind": "primary",
  "routes": {
    "main": "Edit Email"
  },
  "steps": [
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
      "text": "The outgoing correspondence retains the submitted subject, content, recipient addresses, signature and related-subject fields exposed in its editor. Sender and creation date remain presentation/default facts; the save retains modifying account and update time.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content",
            "To",
            "CC",
            "BCC",
            "Signature",
            "Company",
            "Contact person",
            "Lead",
            "Deal",
            "Request",
            "Modified by",
            "Updated"
          ]
        },
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
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

# Edit Email

## Trigger

Operator invokes Edit Email.

## Outcome

The outgoing correspondence retains the submitted subject, content, recipient addresses, signature and related-subject fields exposed in its editor. Sender and creation date remain presentation/default facts; the save retains modifying account and update time.

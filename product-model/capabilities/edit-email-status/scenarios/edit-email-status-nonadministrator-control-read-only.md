---
{
  "kind": "validation",
  "routes": {
    "main": "Edit Email status — nonadministrator control read only"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current account is not a Superuser.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Open the CRM Email editor and inspect available inputs.",
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
      "text": "Incoming, Sent and Trash are absent from CRM editable inputs and remain unchanged. Attempting the administration route redirects to CRM.",
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/admin_redirect_middleware.py"
    }
  ]
}
---

# Edit Email status — nonadministrator control read only

## Trigger

Operator inspects the CRM Email record and attempts the administration route.

## Outcome

No flag input is exposed by CRM; the administration route returns the request to CRM and flags remain unchanged.

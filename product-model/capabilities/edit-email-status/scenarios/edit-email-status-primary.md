---
{
  "kind": "primary",
  "routes": {
    "main": "Edit Email status"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "Open the administration Email editor and submit Incoming, Sent and Trash.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::restricted-administration"
        }
      }
    },
    {
      "kind": "product",
      "text": "The administration Email record retains the submitted Incoming, Sent and Trash values.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Incoming",
            "Sent",
            "Trash"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::restricted-administration"
        }
      },
      "actor": "crm-administrator"
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

# Edit Email status

## Trigger

CRM administrator submits the Email flag fields in administration.

## Outcome

The selected Email retains the submitted flags.

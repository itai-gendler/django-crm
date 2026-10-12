---
{
  "kind": "primary",
  "routes": {
    "main": "Edit Email — linked manager fallback"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Outgoing correspondence without a mailbox UID is owned by another account and links to the initiating Sales manager’s owned/co-owned commercial record.",
      "entities": [],
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Edit the outgoing correspondence subject and recipient addresses.",
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
      "text": "The submitted correspondence subject and recipient addresses are saved. The other owner’s content is presented readonly and remains unchanged; incoming/UID and content exposure continue to follow their source-specific branches.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Subject",
            "To",
            "CC",
            "BCC",
            "Modified by",
            "Updated"
          ]
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "sales-manager"
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

# Edit Email — linked manager fallback

## Trigger

Sales manager invokes Edit Email.

## Outcome

The submitted correspondence subject and recipient addresses are saved. The other owner’s content is presented readonly and remains unchanged; incoming/UID and content exposure continue to follow their source-specific branches.

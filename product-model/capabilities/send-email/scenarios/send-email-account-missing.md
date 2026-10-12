---
{
  "kind": "validation",
  "routes": {
    "main": "Send Email — account missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "No usable account exists for this operation; sending uses the correspondence owner’s main account.",
      "entities": []
    },
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
      "text": "The Email owner's main account is absent. The saved draft remains unchanged in Sent, its editor reopens and the missing-main-account error is presented.",
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

# Send Email — account missing

## Trigger

Operator invokes Send Email.

## Outcome

The Email owner's main account is absent. The saved draft remains unchanged in Sent, its editor reopens and the missing-main-account error is presented.

---
{
  "kind": "edge",
  "routes": {
    "main": "Send mailing out — sender account disabled"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The campaign send raises authentication or sender refusal for its selected sending account.",
      "entities": [],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Authentication failure disables the sender account without delivery.",
      "entities": [
        {
          "entity": "email-account",
          "effect": "changes",
          "facts": [
            "Mass mailing",
            "Report"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/admin_actions.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/utils/sendmassmail.py"
    }
  ]
}
---

# Send mailing out — sender account disabled

## Trigger

The configured processing condition occurs.

## Outcome

Authentication failure disables the sender account without delivery.

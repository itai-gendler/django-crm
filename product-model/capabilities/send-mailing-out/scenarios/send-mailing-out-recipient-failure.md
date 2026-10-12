---
{
  "kind": "edge",
  "routes": {
    "main": "Send mailing out — recipient failure"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Sending to a pending campaign recipient raises a caught recipient/message error.",
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
      "text": "Failed-recipient list and counters/report are updated.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "changes",
          "facts": [
            "Status",
            "Pending recipients",
            "Successful recipients",
            "Failed recipients",
            "Successful count",
            "Failed count",
            "Daily count",
            "Sending date",
            "Report"
          ]
        },
        {
          "entity": "email-account",
          "effect": "changes",
          "facts": [
            "Daily date",
            "Daily count",
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

# Send mailing out — recipient failure

## Trigger

The configured processing condition occurs.

## Outcome

Failed history and counters/report are updated.

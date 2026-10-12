---
{
  "kind": "primary",
  "routes": {
    "main": "Send mailing out"
  },
  "steps": [
    {
      "kind": "condition",
      "unattended": true,
      "text": "Campaign processing is due on the configured schedule.",
      "entities": []
    },
    {
      "kind": "product",
      "text": "Process Active campaign queues under configured schedule, accounts and daily limits. Done can retain failed-recipient list.",
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

# Send mailing out

## Trigger

The configured processing condition occurs.

## Outcome

Process Active campaign queues under configured schedule, accounts and daily limits. Done can retain failure history.

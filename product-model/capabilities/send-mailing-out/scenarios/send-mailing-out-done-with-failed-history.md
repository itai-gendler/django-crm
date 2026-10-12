---
{
  "kind": "primary",
  "routes": {
    "main": "Send mailing out — done with failed history"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The campaign’s pending queue is exhausted while failed-recipient list remains.",
      "entities": [
        {
          "entity": "history",
          "effect": "reads",
          "facts": []
        }
      ],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Done retains failed-recipient list.",
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

# Send mailing out — done with failed history

## Trigger

The configured processing condition occurs.

## Outcome

Done retains failed-recipient history.

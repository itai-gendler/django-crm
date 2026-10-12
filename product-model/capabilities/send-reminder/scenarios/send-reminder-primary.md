---
{
  "kind": "primary",
  "routes": {
    "main": "Send reminder"
  },
  "steps": [
    {
      "kind": "condition",
      "unattended": true,
      "text": "The retained interval makes notice processing due.",
      "entities": []
    },
    {
      "kind": "product",
      "text": "Emit notices for due active reminders, optionally email, deactivate and clear related reminder flags. Create missing canonical interval settings when the sender encounters them.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "changes",
          "facts": [
            "Active",
            "Email notification"
          ]
        },
        {
          "entity": "user-profile",
          "effect": "changes",
          "facts": [
            "Retained notices"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/reminderadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/reminders_sender.py"
    }
  ]
}
---

# Send reminder

## Trigger

The configured processing condition occurs.

## Outcome

Emit notices for due active reminders, optionally email, deactivate and clear related reminder flags. Create missing canonical interval settings when the sender encounters them.

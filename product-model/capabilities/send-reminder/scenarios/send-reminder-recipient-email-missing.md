---
{
  "kind": "edge",
  "routes": {
    "main": "Send reminder — recipient email missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The due notification has email enabled but its owner has no email address.",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Email address"
          ]
        }
      ],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The in-product reminder is retained and deactivated; administrators receive the missing-email report.",
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
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
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

# Send reminder — recipient email missing

## Trigger

The configured processing condition occurs.

## Outcome

The in-product reminder is retained and deactivated; administrators receive the missing-email report.

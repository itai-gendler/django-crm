---
{
  "kind": "edge",
  "routes": {
    "main": "Send reminder — bootstrap check settings"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The sender finds no canonical interval configuration record.",
      "entities": [
        {
          "entity": "reminder-settings",
          "effect": "reads",
          "facts": []
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
      "text": "Missing canonical interval settings are created from the configured fallback or 300 seconds.",
      "entities": [
        {
          "entity": "reminder-settings",
          "effect": "creates",
          "facts": [
            "Check interval"
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

# Send reminder — bootstrap check settings

## Trigger

The configured processing condition occurs.

## Outcome

Missing canonical interval settings are created from the configured fallback or 300 seconds.

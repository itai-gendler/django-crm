---
{
  "kind": "primary",
  "routes": {
    "main": "Delete reminder"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Reminder and invoke delete.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Remove the selected Reminder.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-record"
        }
      },
      "actor": "co-worker"
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

# Delete reminder

## Trigger

Co worker invokes Delete reminder.

## Outcome

Remove the selected Reminder.

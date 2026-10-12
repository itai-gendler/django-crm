---
{
  "kind": "primary",
  "routes": {
    "main": "Edit reminder — reactivate"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The retained Reminder is inactive and the editor sets Active.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Reminder and invoke edit.",
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
      "text": "The Reminder remains retained and active.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "changes",
          "facts": [
            "Subject",
            "Description",
            "Due time",
            "Active",
            "Email notification",
            "Related subject"
          ]
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

# Edit reminder — reactivate

## Trigger

Co worker invokes Edit reminder.

## Outcome

The Reminder remains retained and active.

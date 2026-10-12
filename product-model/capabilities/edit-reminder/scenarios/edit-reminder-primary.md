---
{
  "kind": "primary",
  "routes": {
    "main": "Edit reminder"
  },
  "steps": [
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
      "text": "The selected Reminder retains the submitted Subject, Description, Due time, Active, Email notification, Related subject. Read-only fields retain their previous values and invalid form input returns field errors.",
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

# Edit reminder

## Trigger

Co worker invokes Edit reminder.

## Outcome

The selected Reminder retains the submitted Subject, Description, Due time, Active, Email notification, Related subject. Read-only fields retain their previous values and invalid form input returns field errors.

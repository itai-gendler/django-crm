---
{
  "kind": "primary",
  "routes": {
    "main": "Create reminder"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save the notice subject, description, due time and notification choices.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The retained Reminder belongs to the current account and selected related subject, with the supplied due time and notification choices.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "creates",
          "facts": [
            "Subject",
            "Description",
            "Due time",
            "Active",
            "Email notification",
            "Owner",
            "Related subject",
            "Created"
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

# Create reminder

## Trigger

Co worker invokes Create reminder.

## Outcome

The retained Reminder belongs to the current account and selected related subject, with the supplied due time and notification choices.

---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      },
      "capability": "create-reminder"
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
      "actor": "co-worker",
      "capability": "create-reminder"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "create-reminder",
      "text": "The Product opens the scheduled-notice browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-record"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Reminder and invoke browse.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-browser"
        }
      },
      "capability": "browse-reminders"
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": [
            "Subject",
            "Due time",
            "Active",
            "Related subject",
            "Created"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::reminder-browser"
        }
      },
      "actor": "co-worker",
      "capability": "browse-reminders"
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

# Schedule reminder — nonpopup list

## Trigger

The co worker starts by save the notice subject, description, due time and notification choices.

## Outcome

The participant saves a new Reminder without the popup option and reaches the scheduled-notice browser with its retained due time and activity indication.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "reminder-settings",
      "effect": "creates"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/reminders_sender.py"
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "entity": "product-settings",
          "fact": "Testing",
          "is": false
        },
        {
          "entity": "product-settings",
          "fact": "Debug",
          "is": false
        }
      ]
    }
  ]
}
---

# Reminder settings creation permissions

Creates missing canonical reminder settings; unattended sender under its actual operating gates.

---
{
  "entities": [
    {
      "entity": "reminder",
      "shows": [
        "Subject",
        "Description",
        "Due time",
        "Active",
        "Email notification",
        "Owner",
        "Related subject",
        "Created"
      ],
      "collects": [
        "Subject",
        "Description",
        "Due time",
        "Active",
        "Email notification"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ]
}
---

# Reminder record

Subject/body, related subject, due time, active and notification choices.

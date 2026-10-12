---
{
  "entities": [
    {
      "entity": "project",
      "shows": [
        "Name",
        "Description",
        "Note",
        "Priority",
        "Stage",
        "Active",
        "Start date",
        "Due date",
        "Closing date",
        "Next step",
        "Next step date",
        "Reminder",
        "Owner",
        "Co-owner",
        "Department",
        "Responsible people",
        "Subscribers",
        "Tags",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Name",
        "Description",
        "Note",
        "Priority",
        "Stage",
        "Due date",
        "Next step",
        "Next step date",
        "Reminder",
        "Co-owner",
        "Responsible people",
        "Subscribers",
        "Tags"
      ]
    },
    {
      "entity": "work-stage",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "task-tag",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "user",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "department",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "activity-log",
      "shows": [
        "Entries"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Filename",
        "Media location"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/project.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ]
}
---

# Project record

Work content, stage, dates/follow-up, responsibility, subscribers, tags, linked Tasks and workflow.

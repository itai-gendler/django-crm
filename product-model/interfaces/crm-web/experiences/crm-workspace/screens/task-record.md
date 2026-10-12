---
{
  "entities": [
    {
      "entity": "task",
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
        "Completion token",
        "Hide main task",
        "Owner",
        "Co-owner",
        "Department",
        "Responsible people",
        "Subscribers",
        "Tags",
        "Parent task",
        "Project",
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
        "Hide main task",
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
      "entity": "project",
      "shows": [
        "Name"
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
      "target": "tasks/models/task.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ]
}
---

# Task record

Work content, stage, priority, dates/follow-up, owner/co-owner, responsible people, subscribers, tags, parent/Project, workflow and files.

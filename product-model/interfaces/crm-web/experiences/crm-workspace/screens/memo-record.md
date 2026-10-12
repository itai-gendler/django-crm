---
{
  "entities": [
    {
      "entity": "memo",
      "shows": [
        "Name",
        "Description",
        "Conclusion",
        "Owner",
        "Recipient",
        "Department",
        "Draft",
        "Notified",
        "Stage",
        "Resolution",
        "Review date",
        "Deal",
        "Task",
        "Project",
        "Subscribers",
        "Tags",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Name",
        "Description",
        "Conclusion",
        "Recipient",
        "Draft",
        "Stage",
        "Resolution",
        "Deal",
        "Task",
        "Project",
        "Subscribers"
      ]
    },
    {
      "entity": "resolution",
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
      "entity": "deal",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "task",
      "shows": [
        "Name"
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
      "target": "tasks/models/memo.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    }
  ]
}
---

# Memo record

Author/recipient, content, draft, processing stage, resolution/review, subscribers, linked work/Deal and files.

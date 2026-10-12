---
{
  "actors": [
    "co-worker"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ]
}
---

# Resolve memo through project

## Goal

Resolve Memo through Project.

## Success criterion

The participant saves the Memo using Create project, reaches the prefilled work Add form and saves a new Project. An unreviewed Memo gains its reviewed stage, work reference, generated conclusion and review date, and selected attachments are copied.

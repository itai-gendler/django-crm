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
      "target": "tasks/site/taskadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/forms.py"
    }
  ]
}
---

# Resolve memo through task

## Goal

Resolve Memo through work.

## Success criterion

The participant saves the Memo using Create task, reaches the prefilled work Add form and saves a new Task. An unreviewed Memo gains its reviewed stage, work reference, generated conclusion and review date, and selected attachments are copied.

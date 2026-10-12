---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "memo"
    },
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "project"
    },
    {
      "type": "entity",
      "id": "file"
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
      "target": "tasks/models/task.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/project.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/memoadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ]
}
---

# Memo work resolution

Derived work updates Memo link/stage/review/conclusion, copies selected files and subscribes the implemented Memo owner.

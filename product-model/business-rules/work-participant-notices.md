---
{
  "appliesTo": [
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
      "id": "user-profile"
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
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/userprofileadmin.py"
    }
  ]
}
---

# Work participant notices

Work membership/stage changes emit notices at inspected call sites.

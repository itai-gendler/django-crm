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

# Work assignment and dates

Responsible people required; subtask has at most one; source choices and date validation retained.

Work co-owner choices consult the actual initiating account’s Group names and selected department: on Add, an account without Chief or Task operator uses chiefs when it belongs to department heads, otherwise department heads in its selected department with the first as initial choice. Subscriber choices use active Users. Required responsible membership and the changed subtask maximum of one responsible person are validated separately; changed past due/next-step dates are rejected. Group membership and permissions remain retained account configuration, not new eligibility facts.

---
{
  "actors": [
    "department-head"
  ],
  "references": [
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/projectadmin.py"
    }
  ]
}
---

# Create project from task

## Goal

Create a distinct Project using content and participant defaults copied from an eligible Task.

## Success criterion

The department head saves the source Task through its Create project submit control, reaches the prefilled Add form and saves a distinct Project. The source is retained; no persistent back-link is created.

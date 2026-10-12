---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    }
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
    }
  ],
  "domain": "tasks"
}
---

# Edit task follow up

Next step/date and reminder facts are saved under the source follow-up field policy; workflow recording follows its observed call sites.

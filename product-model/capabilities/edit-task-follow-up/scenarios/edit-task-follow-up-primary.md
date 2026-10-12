---
{
  "kind": "primary",
  "routes": {
    "main": "Edit task follow up"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Task and invoke edit.",
      "entities": [
        {
          "entity": "task",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Next step/date and reminder facts are saved under the source follow-up field policy; workflow recording follows its observed call sites.",
      "entities": [
        {
          "entity": "task",
          "effect": "changes",
          "facts": [
            "Next step",
            "Next step date",
            "Reminder"
          ]
        },
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::task-record"
        }
      },
      "actor": "co-worker"
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
  ]
}
---

# Edit task follow up

## Trigger

Co worker invokes Edit task follow up.

## Outcome

Next step/date and reminder facts are saved under the source follow-up field policy; workflow recording follows its observed call sites.

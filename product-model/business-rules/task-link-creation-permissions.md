---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::public::task-completion"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/task_completed.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/create_completed_subtask.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tests/utils/helpers.py"
    }
  ],
  "permits": [
    {
      "actors": [
        "task-link-holder"
      ],
      "configuredBy": "user"
    }
  ]
}
---

# Task link creation permissions

The actual initiator is Task link holder. The callback resolves Task by supplied token and resolves User by URL object_id. The internal client authenticates as that selected User and dispatches native Task work under its actual direct permissions, assigned Group permissions and native Superuser handling. Site access, native permissions, queryset/object checks and field restrictions apply under that selected account. The selected User is not established as the public caller; the outer caller's department/session selection is not transferred.

Creating a completed participant subtask requires that selected User to pass native Task Add. Parent consequences of its successful child save use the initiating Add authority without a separate parent Change call.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task",
      "effect": "changes",
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

# Task link editing permissions

The actual initiator is Task link holder. The callback resolves Task by supplied token and resolves User by URL object_id. The internal client authenticates as that selected User and dispatches native Task work under its actual direct permissions, assigned Group permissions and native Superuser handling. Site access, native permissions, queryset/object checks and field restrictions apply under that selected account. The selected User is not established as the public caller; the outer caller's department/session selection is not transferred.

Direct existing Task completion uses the selected User native Change, lookup and ordered work-object checks. Parent changes caused by successfully adding/completing a child follow the authorized initiating operation and do not separately require parent Change. Native Change permission is checked first; for an existing object, owner/co-owner or Superuser/Chief/Task operator is accepted, otherwise only its sole responsible person is accepted. Existing-object lookup scope remains required. Automatic parent changes from a successfully saved child follow that initiating operation, without an independent parent Change check.

Task/Project lookup does not inherit CRM department filtering. Superuser, Chief and Task operator receive the base queryset. Others use actual owner, co-owner, responsibility or subscriber membership; Tasks additionally include parent subscribers. The conditional expansion tests self.model.__class__ == Task, exactly as implemented, rather than an intended comparison. BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

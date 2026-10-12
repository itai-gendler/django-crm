---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::task-record"
        }
      ]
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
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/basemodeladmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Task editing permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native Change permission is checked first; for an existing object, owner/co-owner or Superuser/Chief/Task operator is accepted, otherwise only its sole responsible person is accepted. Existing-object lookup scope remains required. Automatic parent changes from a successfully saved child follow that initiating operation, without an independent parent Change check.

Task/Project lookup does not inherit CRM department filtering. Superuser, Chief and Task operator receive the base queryset. Others use actual owner, co-owner, responsibility or subscriber membership; Tasks additionally include parent subscribers. The conditional expansion tests self.model.__class__ == Task, exactly as implemented, rather than an intended comparison. BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

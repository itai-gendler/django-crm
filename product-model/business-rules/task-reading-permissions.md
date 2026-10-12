---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::task-record"
        },
        {
          "place": "crm-web::crm-workspace::task-browser"
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

# Task reading permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native View or Change permission is checked first. Object view accepts owner/co-owner or Superuser/Chief/Task operator; otherwise Project responsibility/subscription is tested on that Project. Task view tests responsibility/subscription across the implementation's selected current/parent/child query; this is distinct from the list queryset.

Task/Project lookup does not inherit CRM department filtering. Superuser, Chief and Task operator receive the base queryset. Others use actual owner, co-owner, responsibility or subscriber membership; Tasks additionally include parent subscribers. The conditional expansion tests self.model.__class__ == Task, exactly as implemented, rather than an intended comparison. BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

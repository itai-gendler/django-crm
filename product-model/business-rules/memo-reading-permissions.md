---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "memo",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::memo-record"
        },
        {
          "place": "crm-web::crm-workspace::memo-browser"
        }
      ]
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
      "target": "tasks/site/memoadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Memo reading permissions

The corresponding configured effective model permission; preserve ordered Memo queryset/view/change checks. Privileged roles may change; reviewed-owner refusal applies in its branch. Delete requires delete permission and the source change check

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native Memo operations use the actual account's effective model permission. Queryset: Superuser uses the base set; Chief/Task operator excludes other owners' drafts; others see recipient non-drafts, their own Memos or subscriber membership. Object View obtains the native result first. For non-drafts the source tests account membership in (owner, recipient, subscribers.all()) or Chief/Task operator/Superuser; the subscribers QuerySet inside that tuple is not expanded into a general subscriber-view grant. Draft object view accepts its owner. Change requires native Change first; Chief/Task operator/Superuser can change, an ordinary owner cannot change Reviewed, and other accessible native-change cases return true. Delete requires native Delete and the source Change check. Work-derived Memo changes follow the successful initiating Task/Project operation, without an independently invented Memo Change call.

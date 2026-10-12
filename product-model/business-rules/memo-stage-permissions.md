---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "memo",
      "effect": "changes",
      "facts": [
        "Stage",
        "Review date"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::memo-record"
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
      "actors": [
        "crm-administrator",
        "company-executive",
        "task-operator"
      ],
      "configuredBy": "user"
    }
  ]
}
---

# Memo stage permissions

Changes processing stage; administrator/chief/task operator and Memo change.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Every field-control branch also requires successful native change access and actual object lookup; the role/owner grant never bypasses that prerequisite.

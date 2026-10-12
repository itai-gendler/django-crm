---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "memo",
      "effect": "changes",
      "facts": [
        "Draft"
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
      "configuredBy": "user"
    }
  ]
}
---

# Memo draft permissions

Changes draft through the owner’s exposed ordinary control; preserve privileged fieldset branch rather than assuming every privileged owner sees it.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native change access is required. On existing Memos the Superuser/Chief/Task operator fieldset exposes Stage; the ordinary-owner branch exposes Draft. Thus being a privileged owner does not itself expose the existing-record Draft control.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "chat-message",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "chat/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chat/site/chatmessageadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Chat message creation permissions

Native effective model permission and owner/audience queryset and object-view checks, with chief/administrator wider queryset and object-view checks. Editing is not owner-only; save assigns the current editor as author

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

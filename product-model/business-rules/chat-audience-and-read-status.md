---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "chat-message"
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
  ]
}
---

# Chat audience and read status

Recipient required; choices derive from subject/reply audience; view clears unread membership; save makes editor author.

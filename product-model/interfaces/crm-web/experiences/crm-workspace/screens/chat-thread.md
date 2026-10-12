---
{
  "entities": [
    {
      "entity": "chat-message",
      "shows": [
        "Subject",
        "Content",
        "Author",
        "Audience",
        "Unread recipients",
        "Date",
        "Reply",
        "Related subject"
      ],
      "collects": [
        "Content",
        "Author",
        "Audience",
        "Reply",
        "Related subject"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "chat/models.py"
    }
  ]
}
---

# Chat thread

Content, audience, replies, related subject and files.

---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "chat/models.py"
    }
  ],
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Chat message

Content, author, persistent audience, unread recipients, date, reply/topic and related subject; Files

## Information kept

- **Subject** — Subject representation derived from the retained related-record association.
- **Content** — Retained body of the communication.
- **Author** — Account assigned as author by the most recent native save.
- **Audience** — Retained audience membership used to select visible contributions.
- **Unread recipients** — Recipients still carrying the unread indication; presenting or replying acknowledges the current account.
- **Date** — Creation timestamp of the contribution.
- **Reply** — Reference to the earlier contribution being answered.
- **Related subject** — The retained record association used by the corresponding reminder or conversation.

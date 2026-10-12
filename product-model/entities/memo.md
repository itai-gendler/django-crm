---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/memo.py"
    }
  ],
  "domain": "memos",
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Memo

Name/content/conclusion, author/recipient, draft/notified flags, processing stage, resolution/review date; Deal/Task/Project, subscribers, tags and Files. Stages: pending, postponed, reviewed

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Description** — Retained descriptive content.
- **Conclusion** — Retained office-memo processing note, including the generated review note when work is created.
- **Owner** — The account responsible for this record.
- **Recipient** — Selected account to whom the office memo is addressed.
- **Department** — The organizational scope retained on this record.
- **Draft** — Whether the office memo remains an unpublished author draft.
- **Notified** — Whether the implemented office-memo notice has been issued.
- **Stage** — The selected configured processing stage.
- **Resolution** — Selected configured resolution associated with memo processing.
- **Review date** — Date recorded when office-memo review is completed.
- **Deal** — Reference to the related commercial relationship.
- **Task** — Reference to related assigned work.
- **Project** — Reference to the related project.
- **Subscribers** — People retained to follow changes and receive the implemented notices.
- **Tags** — Selected retained classification membership.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

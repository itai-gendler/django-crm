---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "domain": "reminders"
}
---

# Reminder

Subject/body, due time, active and email-notification choices; owner and related subject

## Information kept

- **Subject** — Retained subject or title identifying the communication.
- **Description** — Retained descriptive content.
- **Due time** — Time at which the active reminder becomes due.
- **Active** — Whether this record remains active.
- **Email notification** — Whether this reminder also requests an email notice.
- **Owner** — The account responsible for this record.
- **Related subject** — The retained record association used by the corresponding reminder or conversation.
- **Created** — When the record was created.

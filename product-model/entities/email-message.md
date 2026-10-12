---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_message.py"
    }
  ],
  "domain": "email-messages",
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Email Message

Reusable subject/body, selected Signature and ownership; Files

## Information kept

- **Subject** — Retained subject or title identifying the communication.
- **Content** — Retained body of the communication.
- **Signature** — The selected signing content.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

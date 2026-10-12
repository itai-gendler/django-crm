---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "voip/models.py"
    }
  ]
}
---

# Connection

Owner, active choice, provider/caller identity and number

## Information kept

- **Owner** — The account responsible for this record.
- **Active** — Whether this record remains active.
- **Provider** — Configured mail or telephony provider for this connection.
- **Caller identity** — Configured calling identity sent in the callback operation.
- **Number** — Provider-side connection number used for the outgoing callback.

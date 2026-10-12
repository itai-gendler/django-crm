---
{
  "acts": "external",
  "kind": "person",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/unsubscribes.py"
    }
  ]
}
---

# Newsletter recipient

A person acting through an identified mailing registration and unsubscribe link.

## Information kept

- **Identity** — Identity retained for this recipient.
- **Subject** — Subject retained for this recipient.
- **Routing registration** — Whether an identified mailing registration is retained.
- **Routing account** — Routing account retained for this recipient.
- **Mailing eligibility** — The retained newsletter eligibility choice.
- **Unsubscribe token** — The token identifying this registration; no expiry or single-use guarantee is established.

## States

### Unregistered

No mailing-routing registration is retained.

### Registered

A mailing-routing registration is retained; mailing eligibility remains an independent fact.

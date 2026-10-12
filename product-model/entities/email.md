---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    }
  ],
  "domain": "emails-in-crm",
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Email in CRM

Sender/To/CC/BCC, subject/body/signature, date, ticket, message ID, UID/account metadata and incoming/sent/trash flags; counterparties/Deal and Files

## Information kept

- **Subject** — Title or subject text identifying this communication.
- **Content** — Retained body of the communication.
- **Sender** — Sender address retained with the correspondence.
- **To** — Destination address list.
- **CC** — Copy-recipient address list.
- **BCC** — Blind-copy address list.
- **Signature** — The selected signing content.
- **Date** — Correspondence date retained on import or creation.
- **Ticket** — Inquiry and Deal tracking ticket carried by the correspondence.
- **Message identity** — Original message identifier retained for mail linkage.
- **Mailbox UID** — Identifier of the message in its importing mailbox.
- **Email account** — Mailbox account associated with the imported correspondence.
- **Incoming** — Whether the correspondence is retained as incoming mail.
- **Sent** — Whether normal sending reached its final status save; this does not prove recipient delivery.
- **Trash** — Whether correspondence is marked as trash.
- **Company** — Reference to the related corporate counterparty.
- **Contact person** — Reference to the related contact record.
- **Lead** — Reference to the related potential counterparty.
- **Deal** — Reference to the related commercial relationship.
- **Request** — Reference to the related originating inquiry.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

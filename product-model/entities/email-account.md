---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_account.py"
    }
  ]
}
---

# Email account

Ownership, main/mass-mail/import choices, provider/address/connection configuration, credentials, daily date/count, mailbox cursors/import metadata and report

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Address** — Postal address text retained for the counterparty.
- **Owner** — The account responsible for this record.
- **Co-owner** — The additional account sharing responsibility.
- **Department** — The organizational scope retained on this record.
- **Main account** — Marks the owner’s main account used for ordinary correspondence sending.
- **Mass mailing** — Whether the account is enabled for campaign sending.
- **Import enabled** — Whether mailbox import is enabled.
- **Provider** — Configured mail or telephony provider for this connection.
- **Connection configuration** — Retained remote-mail connection configuration.
- **Credentials** — Retained credentials or tokens used by the configured mailbox connection.
- **Daily date** — Day associated with the account’s sending counter.
- **Daily count** — Sends counted for the retained sending day.
- **Mailbox cursor** — Retained mailbox position used by subsequent imports.
- **Import metadata** — Retained import and account linkage metadata.
- **Report** — Retained sending or account diagnostics and errors.

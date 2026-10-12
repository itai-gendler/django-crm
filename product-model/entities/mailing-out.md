---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/mailing_out.py"
    }
  ],
  "domain": "mailing-outs"
}
---

# Mailing Out

Name/message/type, status, recipient queues/history/counts, daily count, sending information, report and account selection; owner. The status is Paused, Active, Active but Error, Interrupted or Done

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Message** — Selected reusable content sent by this campaign.
- **Recipient type** — The campaign’s Company, Contact person or Lead recipient type.
- **Status** — Retained selected status from the choices listed for this subject.
- **Pending recipients** — Retained object identifiers still in the campaign queue.
- **Successful recipients** — Object identifiers moved into the successful list by sending.
- **Failed recipients** — Object identifiers moved into the failed list after recipient processing errors.
- **Recipient count** — Stored campaign total; merging does not guarantee equality with the deduplicated queue length.
- **Successful count** — Stored total of successful recipient processing.
- **Failed count** — Stored total of recipient processing failures.
- **Daily count** — Sends counted for the retained sending day.
- **Sending date** — Day associated with the campaign’s daily sending count.
- **Report** — Retained sending or account diagnostics and errors.
- **Email account** — Retained sending-account association used by the corresponding routing operation.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

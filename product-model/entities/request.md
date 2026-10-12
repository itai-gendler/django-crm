---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    }
  ],
  "domain": "requests",
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Request

Subject/body, received/contact details, attribution, source, ticket, location, owner/co-owner and pending/duplicate/case/subsequent/verification flags; Products and optional counterparties/Deal

## Information kept

- **Subject** — Retained subject or title identifying the communication.
- **Description** — Retained descriptive content.
- **Remark** — Additional retained inquiry remark.
- **Translation** — Retained translation of descriptive content.
- **Person name** — Name components retained for matching and counterparty creation.
- **Email address** — Address or address list retained for correspondence and counterparty matching.
- **Telephone** — Primary telephone value used in contact display and telephone matching.
- **Company name** — Company name supplied for this person or inquiry.
- **Receipt date** — Date the inquiry was received.
- **Attribution** — Retained website marketing and source-attribution values.
- **Source** — Configured lead-source attribution associated with the record.
- **Ticket** — Tracking identifier shared by the inquiry, corresponding commercial work and linked correspondence.
- **Country** — The selected country for this record.
- **City** — The selected city for this record.
- **Owner** — The account responsible for this record.
- **Co-owner** — The additional account sharing responsibility.
- **Department** — The organizational scope retained on this record.
- **Pending** — Whether the inquiry awaits processing.
- **Duplicate** — Whether the inquiry is marked as a duplicate.
- **Case** — Whether the inquiry is marked as a case excluded by inspected intake reports.
- **Subsequent** — Whether the inquiry is retained as a subsequent contact.
- **Verification required** — Whether processed counterparty details require verification.
- **Products** — Selected catalog items carried into commercial line creation.
- **Company** — Reference to the related corporate counterparty.
- **Contact person** — Reference to the related contact record.
- **Lead** — Reference to the related potential counterparty.
- **Deal** — Reference to the related commercial relationship.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

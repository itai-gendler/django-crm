---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/contact.py"
    }
  ],
  "domain": "contact-persons",
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Contact person

Names/title, personal facts, avatar, phones/emails/address, last contact, source and mailing eligibility; Company and ownership

## Information kept

- **First name** — Given name retained for identifying the person.
- **Last name** — Family name retained for identifying the person.
- **Title** — Selected personal form of address.
- **Birth date** — Retained date of birth.
- **Sex** — Selected personal sex information.
- **Avatar** — Uploaded image representing the person or account.
- **Description** — Retained descriptive content.
- **Telephone** — Primary telephone value used in contact display and telephone matching.
- **Other telephone** — Additional telephone value retained for contact and caller matching.
- **Mobile** — Mobile telephone value retained for contact and caller matching.
- **Email address** — Address or address list retained for correspondence and counterparty matching.
- **Address** — Postal address text retained for the counterparty.
- **Country** — The selected country for this record.
- **City** — The selected city for this record.
- **Last contact** — Date or time of the latest contact recorded by the implemented contact and PBX paths.
- **Source** — Configured lead-source attribution associated with the record.
- **Mailing eligibility** — The retained choice used by campaign selection and unsubscribe.
- **Company** — Reference to the related corporate counterparty.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

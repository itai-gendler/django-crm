---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/lead.py"
    }
  ],
  "domain": "leads",
  "relations": [
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Lead

Provisional person/company information, contact/qualification facts, avatar, source, mailing eligibility and ownership; industries and conversion references

## Information kept

- **First name** — Given name retained for identifying the person.
- **Last name** — Family name retained for identifying the person.
- **Title** — Selected personal form of address.
- **Avatar** — Uploaded image representing the person or account.
- **Company name** — Company name supplied for this person or inquiry.
- **Description** — Retained descriptive content.
- **Qualification** — Retained classification of the counterparty’s relationship.
- **Telephone** — Primary telephone value used in contact display and telephone matching.
- **Other telephone** — Additional telephone value retained for contact and caller matching.
- **Mobile** — Mobile telephone value retained for contact and caller matching.
- **Email address** — Address or address list retained for correspondence and counterparty matching.
- **Website** — Website address retained with the counterparty or inquiry.
- **Address** — Postal address text retained for the counterparty.
- **Country** — The selected country for this record.
- **City** — The selected city for this record.
- **Last contact** — Date or time of the latest contact recorded by the implemented contact and PBX paths.
- **Source** — Configured lead-source attribution associated with the record.
- **Client types** — Selected configured counterparty classifications.
- **Industries** — Selected industry memberships.
- **Tags** — Selected retained classification membership.
- **Mailing eligibility** — The retained choice used by campaign selection and unsubscribe.
- **Company** — Reference to the related corporate counterparty.
- **Contact person** — Reference to the related contact record.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

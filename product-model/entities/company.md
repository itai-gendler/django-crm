---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/company.py"
    }
  ],
  "domain": "companies",
  "relations": [
    {
      "entity": "contact-person",
      "verb": "has contact",
      "cardinality": "one-to-many"
    },
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Company

Corporate/alternative names, registration/contact/address details, classification, qualification, mailing eligibility and ownership; Contacts, industries and tags

## Information kept

- **Full name** — Full corporate name used for recognition and correspondence.
- **Alternative names** — Additional names used for recognition and matching.
- **Registration number** — Retained company registration identifier.
- **Logo** — Uploaded company logo image.
- **Description** — Retained descriptive content.
- **Qualification** — Retained classification of the counterparty’s relationship.
- **Telephone** — Primary telephone value used in contact display and telephone matching.
- **Other telephone** — Additional telephone value retained for contact and caller matching.
- **Email address** — Address or address list retained for correspondence and counterparty matching.
- **Website** — Website address retained with the counterparty or inquiry.
- **Address** — Postal address text retained for the counterparty.
- **Country** — The selected country for this record.
- **City** — The selected city for this record.
- **Client types** — Selected configured counterparty classifications.
- **Industries** — Selected industry memberships.
- **Tags** — Selected retained classification membership.
- **Mailing eligibility** — The retained choice used by campaign selection and unsubscribe.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

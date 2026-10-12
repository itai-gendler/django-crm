---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    }
  ],
  "domain": "deals",
  "relations": [
    {
      "entity": "output",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "payment",
      "verb": "has payment",
      "cardinality": "one-to-many"
    },
    {
      "entity": "transaction-quality-event",
      "verb": "has quality event",
      "cardinality": "one-to-many"
    },
    {
      "entity": "file",
      "verb": "has attachment",
      "cardinality": "one-to-many"
    },
    {
      "entity": "activity-log",
      "verb": "has workflow",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Deal

Commercial content, amount/currency, pricing/discount choices, stage/dates, activity/relevance/importance, closing reason/dates, follow-up and responsibility; Request, counterparties, Outputs, Payments, Emails, Memos, quality and workflow

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Description** — Retained descriptive content.
- **Translation** — Retained translation of descriptive content.
- **Amount** — The retained monetary amount; interpretation and conversion follow the operation’s own rules.
- **Currency** — The monetary unit of the retained amount.
- **Tier name** — The configured Client Type naming this price tier.
- **Discount type** — Selected percentage or monetary discount mode.
- **Discount** — Retained discount value used in line pricing.
- **Stage** — The selected configured processing stage.
- **Stage dates** — Retained stage-transition dates and labels.
- **Active** — Whether this record remains active.
- **Relevant** — Whether commercial work is relevant; clearing this closes activity in the save branch.
- **Important** — Retained importance mark.
- **New** — Whether the owner has yet to acknowledge the new commercial record.
- **Closing reason** — Selected department closing reason controlling activity and successful-stage effects.
- **Closing date** — Date recorded by the implemented closure branch.
- **Successful closing date** — Retained win timestamp set by the implemented success-stage branches.
- **Next step** — The retained follow-up action.
- **Next step date** — The retained follow-up date.
- **Reminder** — Whether the subject carries an active reminder indication.
- **Owner** — The account responsible for this record.
- **Co-owner** — The additional account sharing responsibility.
- **Department** — The organizational scope retained on this record.
- **Request** — Reference to the related originating inquiry.
- **Company** — Reference to the related corporate counterparty.
- **Contact person** — Reference to the related contact record.
- **Lead** — Reference to the related potential counterparty.
- **Partner contact** — Selected partner contact for correspondence.
- **Ticket** — Tracking identifier shared by the inquiry, corresponding commercial work and linked correspondence.
- **Tags** — Selected retained classification membership.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

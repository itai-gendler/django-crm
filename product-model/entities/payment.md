---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    }
  ],
  "domain": "payments"
}
---

# Payment

Amount/currency/date, status, commercial references and representative choice; Deal. The status is received, guaranteed, high probability or low probability

## Information kept

- **Amount** — The retained monetary amount; interpretation and conversion follow the operation’s own rules.
- **Currency** — The monetary unit of the retained amount.
- **Payment date** — Date on which the payment is due or received according to its retained status.
- **Status** — Retained selected status from the choices listed for this subject.
- **Contract number** — Commercial contract reference recorded with the payment.
- **Invoice number** — Invoice reference recorded with the payment.
- **Order number** — Order reference recorded with the payment.
- **Through representative** — Whether payment is marked as through a representative when that control is enabled.
- **Deal** — Reference to the related commercial relationship.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

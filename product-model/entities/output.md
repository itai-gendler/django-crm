---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/output.py"
    }
  ],
  "domain": "deals"
}
---

# Output

Product, quantity, amount/currency, planned/contract/actual shipment dates, serial information and shipped flag; Deal

## Information kept

- **Product** — Reference to the catalog item represented by this record.
- **Quantity** — Nonzero quantity retained on the commercial line.
- **Amount** — The retained monetary amount; interpretation and conversion follow the operation’s own rules.
- **Currency** — The monetary unit of the retained amount.
- **Planned shipment date** — Expected shipment date retained on the commercial line.
- **Contract shipment date** — Shipment date required by the contract.
- **Actual shipment date** — Recorded actual shipment date, which sets the shipped indication.
- **Serial information** — Serial-number details associated with the shipped item.
- **Shipped** — Whether the item has been marked shipped by the implemented shipment branch.
- **Deal** — Reference to the related commercial relationship.
- **Created** — When the record was created.
- **Updated** — When the record was last saved.
- **Modified by** — The account retained as the last modifying person.

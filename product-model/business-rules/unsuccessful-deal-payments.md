---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal"
    },
    {
      "type": "entity",
      "id": "payment"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentadmin.py"
    }
  ]
}
---

# Unsuccessful deal payments

Unsuccessful closure removes nonreceived Payments and preserves received ones; no refund behavior.

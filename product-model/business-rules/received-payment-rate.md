---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "payment"
    },
    {
      "type": "entity",
      "id": "currency-rate"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentadmin.py"
    }
  ]
}
---

# Received payment rate

Received Payment can capture a missing dated conversion rate.

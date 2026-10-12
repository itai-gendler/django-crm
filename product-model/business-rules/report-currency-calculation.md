---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "payment"
    },
    {
      "type": "entity",
      "id": "currency"
    },
    {
      "type": "entity",
      "id": "currency-rate"
    },
    {
      "type": "entity",
      "id": "user-session"
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
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/currencyadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/crmsite.py"
    }
  ]
}
---

# Report currency calculation

Financial projections use their own rate fallback/category/VAT rules and Session currency selection.

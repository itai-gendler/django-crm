---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "output"
    },
    {
      "type": "entity",
      "id": "product-price-tier"
    },
    {
      "type": "entity",
      "id": "currency"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/output.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/pricingtier.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/currencyadmin.py"
    }
  ]
}
---

# Output price calculation

Amount uses source tier/discount/conversion calculation; lookup does not enforce tier quantity/date eligibility.

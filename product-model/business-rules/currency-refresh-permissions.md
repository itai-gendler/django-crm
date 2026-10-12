---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "currency",
      "effect": "changes"
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
      "target": "crm/site/currencyadmin.py"
    }
  ],
  "permits": [
    {
      "unattended": true,
      "when": [
        {
          "entity": "product-settings",
          "fact": "Testing",
          "is": false
        }
      ]
    }
  ]
}
---

# Currency refresh permissions

Changes current Currency conversions; configured unattended refresh.

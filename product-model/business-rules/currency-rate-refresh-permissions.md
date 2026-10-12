---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "currency-rate",
      "effect": "changes"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
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

# Currency rate refresh permissions

Changes historical rates through configured refresh.

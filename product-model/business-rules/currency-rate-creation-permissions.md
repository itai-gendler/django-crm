---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "currency-rate",
      "effect": "creates"
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
    },
    {
      "configuredBy": "user"
    }
  ]
}
---

# Currency rate creation permissions

Creates missing historical rate; received-Payment capture or configured unattended refresh.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

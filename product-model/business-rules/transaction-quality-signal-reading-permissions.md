---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction-quality-signal",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::transaction-quality-event-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "quality/models/transaction_quality.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Transaction quality signal reading permissions

Reads signal choices; actual event gate and department-filtered inline choices.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

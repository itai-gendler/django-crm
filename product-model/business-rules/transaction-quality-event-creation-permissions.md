---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction-quality-event",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
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

# Transaction quality event creation permissions

The corresponding configured effective model permission checks; Deal-inline creation/change uses quality change permission plus Deal clarification. Functional mapped creation is the Deal inline; standalone Add leaves Deal read-only

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

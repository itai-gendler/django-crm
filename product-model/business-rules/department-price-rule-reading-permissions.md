---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "department-price-rule",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::product-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/pricingtier.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Department price rule reading permissions

Reads Department pricing configuration during permitted tier/pricing operations.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

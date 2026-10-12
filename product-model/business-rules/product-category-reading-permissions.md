---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product-category",
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
      "target": "crm/models/product.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Product category reading permissions

Reads category choices in permitted Product presentation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

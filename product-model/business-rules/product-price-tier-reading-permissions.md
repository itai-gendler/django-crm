---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product-price-tier",
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
      "target": "crm/site/productadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/tieredpricinginline.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmstackedinline.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Product price tier reading permissions

Reads tiers through permitted Product presentation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

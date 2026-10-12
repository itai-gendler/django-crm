---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "product",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::product-record"
        },
        {
          "place": "crm-web::crm-workspace::product-browser"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/product.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/productadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Product reading permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native Product reading requires the corresponding effective native permission and active staff site access. ProductAdmin uses plain ModelAdmin, without CRM ownership/co-owner clarification. Existing-object lookup uses selected department first, otherwise Superoperator assigned department Groups, otherwise an unfiltered queryset. Product search uses its native name/description search on the supplied Product queryset.

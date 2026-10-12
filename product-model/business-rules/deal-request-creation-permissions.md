---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::request-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Deal request creation permissions

Creates Deal through Request processing; actual Request operation and exposed Deal-change control. Country/product/case checks are validation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

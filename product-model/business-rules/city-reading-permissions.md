---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "city",
      "effect": "reads",
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
      "target": "crm/models/country.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/cityadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# City reading permissions

Reads City information through its mapped presentation; public matching lookup has no additional authorization check.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

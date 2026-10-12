---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "industry",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::company-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/others.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Industry reading permissions

Reads Industry choices through permitted Company/Lead operation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

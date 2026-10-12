---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "output",
      "effect": "changes",
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
      "target": "crm/models/output.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Output inline editing permissions

Changes Output commercial facts; Output change permission plus Deal ownership/department clarification.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

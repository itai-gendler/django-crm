---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "history",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::record-history"
        },
        {
          "place": "crm-web::restricted-administration::global-history"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ],
  "permits": []
}
---

# History removal prohibition

History presentation never permits deleting audit entries.

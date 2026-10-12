---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "history",
      "effect": "changes",
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

# History editing prohibition

History presentation never permits editing audit entries.

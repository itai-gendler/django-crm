---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "history",
      "effect": "creates",
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

# History creation prohibition

Creates History through history presentation; permits: [], excluding automatic recording.

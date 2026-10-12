---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
        },
        {
          "place": "crm-web::crm-workspace::deal-browser"
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
  "permits": []
}
---

# Deal direct add prohibition

Ordinary native Deal Add is forbidden; Request processing creates a Deal through its separately governed operation.

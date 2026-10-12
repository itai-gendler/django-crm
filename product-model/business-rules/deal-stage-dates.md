---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal"
    },
    {
      "type": "entity",
      "id": "deal-stage"
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
      "target": "crm/models/others.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    }
  ]
}
---

# Deal stage dates

Stage changes track dates/success time; observed default-stage advancement retained.

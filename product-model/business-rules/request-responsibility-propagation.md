---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request"
    },
    {
      "type": "entity",
      "id": "deal"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    }
  ]
}
---

# Request responsibility propagation

Request owner/department changes propagate at the inspected save points.

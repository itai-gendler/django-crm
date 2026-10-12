---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request"
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
      "target": "crm/site/requestadmin.py"
    }
  ]
}
---

# Request processing flags

Pending/duplicate/case transitions follow actual processing branches.

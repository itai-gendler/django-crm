---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request"
    },
    {
      "type": "entity",
      "id": "lead-source"
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
      "target": "crm/models/others.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    }
  ]
}
---

# Inquiry source resolution

Public/API creation follows distinct source lookup, method and response branches.

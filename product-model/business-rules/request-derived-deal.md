---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal"
    },
    {
      "type": "entity",
      "id": "output"
    },
    {
      "type": "entity",
      "id": "file"
    },
    {
      "type": "entity",
      "id": "request"
    },
    {
      "type": "entity",
      "id": "email"
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
      "target": "crm/models/output.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    }
  ]
}
---

# Request derived deal

Deal, Outputs and attachment references are created; inquiry context/defaults copied and Request/Email references updated.

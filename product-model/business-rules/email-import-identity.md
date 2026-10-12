---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email"
    },
    {
      "type": "entity",
      "id": "request"
    },
    {
      "type": "entity",
      "id": "file"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ]
}
---

# Email import identity

Duplicate identifiers, CRM-origin skips, ticket linkage, attachments and inquiry creation follow inspected import branches.

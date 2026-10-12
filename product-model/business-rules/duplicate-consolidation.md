---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "company"
    },
    {
      "type": "entity",
      "id": "contact-person"
    },
    {
      "type": "entity",
      "id": "lead"
    },
    {
      "type": "entity",
      "id": "newsletter-recipient"
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
      "target": "crm/models/company.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/contact.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/lead.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/unsubscribes.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/contactadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ]
}
---

# Duplicate consolidation

Fill missing original facts, reparent/union supported relationships, update mailing references and remove duplicate/registration.

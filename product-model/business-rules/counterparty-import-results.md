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
    }
  ]
}
---

# Counterparty import results

Queued import uses subject-specific duplicate keys and preserves unmatched-company/row-error outcomes.

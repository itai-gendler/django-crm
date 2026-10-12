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
      "target": "crm/site/companyadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/contactadmin.py"
    }
  ]
}
---

# Company ownership transfer

Selected Company transfer also changes corresponding Contacts’ owner/department.

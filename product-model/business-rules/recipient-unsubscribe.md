---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "newsletter-recipient"
    },
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
      "id": "mailing-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/unsubscribes.py"
    },
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
      "target": "settings/models.py"
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

# Recipient unsubscribe

Found registration disables its and linked subject’s mailing eligibility; unknown token redirects without mutation.

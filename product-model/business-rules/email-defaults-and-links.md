---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email"
    },
    {
      "type": "entity",
      "id": "file"
    },
    {
      "type": "entity",
      "id": "signature"
    },
    {
      "type": "entity",
      "id": "email-account"
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
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/signature.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_account.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/signatureadmin.py"
    }
  ]
}
---

# Email defaults and links

Draft creation supplies source defaults, addresses, signature, ticket, subject links and selected attachments.

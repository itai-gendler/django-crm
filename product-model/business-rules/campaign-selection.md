---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out"
    },
    {
      "type": "entity",
      "id": "newsletter-recipient"
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
      "target": "massmail/models/mailing_out.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/unsubscribes.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_account.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    }
  ]
}
---

# Campaign selection

Selection validates owner/type/eligibility/account prerequisites and creates observed queue information.

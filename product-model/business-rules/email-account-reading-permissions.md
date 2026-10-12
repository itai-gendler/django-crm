---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-account",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_account.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email account reading permissions

Reads account choices/default information under the actual compose/import/campaign path; explicit-ID helper exceptions retained.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

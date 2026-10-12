---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      ]
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
      "target": "massmail/site/mailingoutadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Mailing out removal permissions

Selected-counterparty creation follows permitted counterparty action and selection scope. Native record read/change/delete follows Mailing Out checks. Filtered creation and merge consequences use additional Rules

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

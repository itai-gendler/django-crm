---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "newsletter-recipient",
      "effect": "changes",
      "facts": [
        "Routing registration",
        "Routing account",
        "Unsubscribe token"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::company-browser"
        },
        {
          "place": "crm-web::crm-workspace::contact-person-browser"
        },
        {
          "place": "crm-web::crm-workspace::lead-browser"
        }
      ],
      "to": "Unregistered"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/admin_actions.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Recipient vip removal permissions

Removes registration/token through permitted counterparty action; no common-owner prerequisite.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

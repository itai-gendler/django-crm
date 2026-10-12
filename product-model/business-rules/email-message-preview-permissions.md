---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-message",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/message_previews.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email message preview permissions

Reads reusable-message preview; logged-in handler, current department unless chief/administrator.

The handler requires a logged-in requesting account. It applies the current selected department except for Chief or Superuser, using that actual User’s derived roles and session scope; it performs no separate native source View or ownership check.

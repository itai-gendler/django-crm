---
{
  "kind": "primary",
  "routes": {
    "main": "Sign out — administration logout"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current browser session was established in restricted administration.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "End the current authenticated session.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::restricted-administration"
        }
      }
    },
    {
      "kind": "product",
      "text": "The current administration session ends.",
      "entities": [
        {
          "entity": "user-session",
          "effect": "removes",
          "as": "current-session"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::restricted-administration"
        }
      },
      "actor": "crm-administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ]
}
---

# Sign out — administration logout

## Trigger

CRM administrator invokes Sign out.

## Outcome

The current administration session ends.

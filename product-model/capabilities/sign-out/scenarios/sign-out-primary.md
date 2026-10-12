---
{
  "kind": "primary",
  "routes": {
    "main": "Sign out"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "End the current authenticated session.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      }
    },
    {
      "kind": "product",
      "text": "End the current authenticated session.",
      "entities": [
        {
          "entity": "user-session",
          "effect": "removes",
          "as": "current-session"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      },
      "actor": "co-worker"
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

# Sign out

## Trigger

Co worker invokes Sign out.

## Outcome

End the current authenticated session.

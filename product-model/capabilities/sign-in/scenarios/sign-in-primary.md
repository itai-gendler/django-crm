---
{
  "kind": "primary",
  "routes": {
    "main": "Sign in"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Submit the account credentials.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::public::sign-in"
        }
      }
    },
    {
      "kind": "product",
      "text": "Establish the active staff account’s CRM session after accepted credentials.",
      "entities": [
        {
          "entity": "user-session",
          "effect": "creates",
          "facts": [
            "Current account",
            "Selected department",
            "Report currency"
          ],
          "as": "current-session"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::public::sign-in"
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

# Sign in

## Trigger

Co worker invokes Sign in.

## Outcome

Establish the active staff account’s CRM session after accepted credentials.

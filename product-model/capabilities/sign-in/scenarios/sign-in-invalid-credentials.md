---
{
  "kind": "validation",
  "routes": {
    "main": "Sign in — invalid credentials"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The supplied username/password combination is rejected by sign-in.",
      "entities": []
    },
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
      "text": "Credentials are rejected and no session is created.",
      "entities": [],
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

# Sign in — invalid credentials

## Trigger

Co worker invokes Sign in.

## Outcome

Credentials are rejected and no session is created.

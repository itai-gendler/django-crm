---
{
  "kind": "validation",
  "routes": {
    "main": "Sign in — inactive or nonstaff"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The supplied credentials identify an inactive account or one lacking Staff status.",
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
      "text": "Sign-in is refused for the inactive/nonstaff account.",
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

# Sign in — inactive or nonstaff

## Trigger

Co worker invokes Sign in.

## Outcome

Sign-in is refused for the inactive/nonstaff account.

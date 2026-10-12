---
{
  "kind": "validation",
  "routes": {
    "main": "Edit account status — nonadministrator control unavailable"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current account is not a Superuser and opens account-status presentation.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select User and invoke edit.",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The administrative status control is unavailable and its fact remains unchanged.",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Username",
            "Name",
            "Email address",
            "Active"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-record"
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

# Edit account status — nonadministrator control unavailable

## Trigger

Co worker submits the stated case.

## Outcome

The administrative status control is unavailable and its fact remains unchanged.

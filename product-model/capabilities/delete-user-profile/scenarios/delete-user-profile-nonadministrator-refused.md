---
{
  "kind": "validation",
  "routes": {
    "main": "Delete user profile — nonadministrator refused"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current account is not a Superuser and attempts profile removal.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select User profile and invoke delete.",
      "entities": [
        {
          "entity": "user-profile",
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
      "text": "The profile is not removed.",
      "entities": [
        {
          "entity": "user-profile",
          "effect": "reads",
          "facts": [
            "Avatar",
            "Language",
            "Timezone",
            "Timezone activation"
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
      "target": "common/site/userprofileadmin.py"
    }
  ]
}
---

# Delete user profile — nonadministrator refused

## Trigger

Co worker submits the stated case.

## Outcome

The profile is not removed.

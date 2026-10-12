---
{
  "kind": "validation",
  "routes": {
    "main": "Edit user profile — avatar too large"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted profile image exceeds the form’s accepted file size.",
      "entities": [
        {
          "entity": "file",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "co-worker"
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select User profile and invoke edit.",
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
      "text": "The oversized avatar is rejected and the previous image remains.",
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

# Edit user profile — avatar too large

## Trigger

Co worker invokes Edit user profile.

## Outcome

The oversized avatar is rejected and the previous image remains.

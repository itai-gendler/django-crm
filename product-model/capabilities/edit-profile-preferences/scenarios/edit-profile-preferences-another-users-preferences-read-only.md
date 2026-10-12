---
{
  "kind": "validation",
  "routes": {
    "main": "Edit profile preferences — another users preferences read only"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected profile belongs to a different account from the current editor.",
      "entities": []
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
      "text": "The other user’s language, timezone and notification choices remain unchanged.",
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
        },
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

# Edit profile preferences — another users preferences read only

## Trigger

Co worker invokes Edit profile preferences.

## Outcome

The other user’s language, timezone and notification choices remain unchanged.

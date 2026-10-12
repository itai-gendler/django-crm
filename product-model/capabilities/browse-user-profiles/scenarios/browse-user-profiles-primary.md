---
{
  "kind": "primary",
  "routes": {
    "main": "Browse user profiles"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select User profile and invoke browse.",
      "entities": [
        {
          "entity": "user-profile",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Present the source-defined User profile selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "user-profile",
          "effect": "reads",
          "facts": [
            "Avatar",
            "Language",
            "Timezone",
            "PBX number"
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
          "place": "crm-web::crm-workspace::user-profile-browser"
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

# Browse user profiles

## Trigger

Co worker invokes Browse user profiles.

## Outcome

Present the source-defined User profile selection, search/filter results and summary facts.

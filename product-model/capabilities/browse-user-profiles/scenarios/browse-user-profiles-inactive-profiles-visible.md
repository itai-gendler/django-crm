---
{
  "kind": "primary",
  "routes": {
    "main": "Browse user profiles — inactive profiles visible"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "An inactive account still has a profile present in the unfiltered profile selection.",
      "entities": []
    },
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
      "text": "The source-defined inactive profile entries are included.",
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

# Browse user profiles — inactive profiles visible

## Trigger

Co worker invokes Browse user profiles.

## Outcome

The source-defined inactive profile entries are included.

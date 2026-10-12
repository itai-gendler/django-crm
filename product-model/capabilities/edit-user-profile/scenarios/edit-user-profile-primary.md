---
{
  "kind": "primary",
  "routes": {
    "main": "Edit user profile"
  },
  "steps": [
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
      "text": "The permitted avatar and PBX number are saved; image size validation and saved image processing apply.",
      "entities": [
        {
          "entity": "user-profile",
          "effect": "changes",
          "facts": [
            "Avatar",
            "PBX number"
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

# Edit user profile

## Trigger

Co worker invokes Edit user profile.

## Outcome

The permitted avatar and PBX number are saved; image size validation and saved image processing apply.

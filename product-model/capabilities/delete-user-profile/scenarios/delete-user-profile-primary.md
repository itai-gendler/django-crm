---
{
  "kind": "primary",
  "routes": {
    "main": "Delete user profile"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "crm-administrator",
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
      "text": "Remove the selected User profile.",
      "entities": [
        {
          "entity": "user-profile",
          "effect": "removes"
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
      "actor": "crm-administrator"
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

# Delete user profile

## Trigger

CRM administrator invokes Delete user profile.

## Outcome

Remove the selected User profile.

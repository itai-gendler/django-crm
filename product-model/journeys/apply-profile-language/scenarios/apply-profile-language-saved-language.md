---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      },
      "capability": "edit-profile-preferences"
    },
    {
      "kind": "product",
      "text": "The current account’s language, timezone activation and CRM notification choices are saved.",
      "entities": [
        {
          "entity": "user-profile",
          "effect": "changes",
          "facts": [
            "Language",
            "Timezone",
            "Timezone activation",
            "CRM notifications"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-record"
        }
      },
      "actor": "co-worker",
      "capability": "edit-profile-preferences"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "edit-profile-preferences",
      "text": "The Product opens the account-preferences browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-record"
        }
      }
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
      },
      "capability": "browse-user-profiles"
    },
    {
      "kind": "product",
      "text": "The account-preferences browser presents language and optional timezone alongside account identity, contact email and active status.",
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
      "actor": "co-worker",
      "capability": "browse-user-profiles"
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

# Apply profile language — saved language

## Trigger

The co worker starts by select User profile and invoke edit.

## Outcome

The participant saves their language and timezone/notification preferences, follows the reload to the account-preferences browser and sees the selected language applied.

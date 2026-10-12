---
{
  "kind": "primary",
  "routes": {
    "main": "Edit profile preferences"
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

# Edit profile preferences

## Trigger

Co worker invokes Edit profile preferences.

## Outcome

The current account’s language, timezone activation and CRM notification choices are saved.

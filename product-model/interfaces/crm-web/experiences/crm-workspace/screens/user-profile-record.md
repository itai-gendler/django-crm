---
{
  "entities": [
    {
      "entity": "user-profile",
      "shows": [
        "Avatar",
        "Language",
        "Timezone",
        "Timezone activation",
        "PBX number",
        "CRM notifications",
        "Retained notices"
      ],
      "collects": [
        "Avatar",
        "Language",
        "Timezone",
        "Timezone activation",
        "PBX number",
        "CRM notifications"
      ]
    },
    {
      "entity": "user",
      "shows": [
        "Username",
        "Name",
        "Email address",
        "Active"
      ],
      "collects": [
        "Active"
      ]
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

# User profile record

Account identity/status, avatar, language/timezone, PBX number and notification preferences.

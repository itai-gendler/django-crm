---
{
  "entities": [
    {
      "entity": "user-profile",
      "shows": [
        "Avatar",
        "Language",
        "Timezone",
        "PBX number"
      ]
    },
    {
      "entity": "user",
      "shows": [
        "Username",
        "Name",
        "Email address",
        "Active"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/userprofileadmin.py"
    }
  ]
}
---

# User profile browser

Account username, name, contact email/PBX number, language and active status; current timezone is additionally shown when configured.

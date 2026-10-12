---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "domain": "user-profiles"
}
---

# User profile

Avatar, language, timezone/activation, PBX number, CRM notification preference and retained notices; one User

## Information kept

- **Avatar** — Uploaded image representing the person or account.
- **Language** — Selected interface language code.
- **Timezone** — Selected UTC timezone.
- **Timezone activation** — Whether the account’s selected timezone is activated.
- **PBX number** — Account’s internal PBX contact number.
- **CRM notifications** — Whether the account requests CRM email notifications.
- **Retained notices** — Saved messages presented to this account.

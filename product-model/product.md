---
{
  "id": "django-crm",
  "summary": "Receive inquiries, manage counterparties and Deals, coordinate work, handle correspondence and mailing campaigns, and review commercial activity.",
  "category": "crm",
  "tags": [
    "crm",
    "sales",
    "tasks",
    "email"
  ],
  "license": "AGPL-3.0-only",
  "limitations": [
    "Staff work in Django Admin screens; integrations that need a REST API add one with third-party Django packages.",
    "Mail is sent and received through the organization's own email accounts over SMTP and IMAP.",
    "Mailings from a sales manager's main email account go only to VIP recipients; other recipients are reached through additional accounts.",
    "Each email account sends at most the configured number of mailing messages per day, optionally only during business hours.",
    "Only email tied to a Request or Deal by its ticket is imported automatically."
  ],
  "languages": [
    "ar",
    "cs",
    "de",
    "el",
    "en",
    "es",
    "fr",
    "he",
    "hi",
    "id",
    "it",
    "ja",
    "ko",
    "nl",
    "pl",
    "pt-br",
    "ro",
    "ru",
    "tr",
    "uk",
    "vi",
    "zh-hans"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "README.md"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/settings.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/urls.py"
    }
  ]
}
---

# DjangoCRM

DjangoCRM receives inquiries, manages Companies, Contact persons, Leads and Deals, coordinates Tasks, Projects and Memos, handles correspondence and mailing campaigns, and presents reports, reminders, chat and history.

## Intent

Give small and mid-size businesses one self-hosted system for inquiries, sales, tasks, correspondence and mailings, keeping each commercial record connected to the others while it follows its own lifecycle.

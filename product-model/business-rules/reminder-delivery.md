---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "reminder"
    },
    {
      "type": "entity",
      "id": "user-profile"
    },
    {
      "type": "entity",
      "id": "reminder-settings"
    },
    {
      "type": "entity",
      "id": "product-settings"
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
      "target": "settings/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/settings.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/userprofileadmin.py"
    }
  ]
}
---

# Reminder delivery

Due active reminders emit notice, optionally email, deactivate and clear the related reminder flag; missing canonical interval settings can be created.

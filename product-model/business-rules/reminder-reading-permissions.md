---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "reminder",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::reminder-record"
        },
        {
          "place": "crm-web::crm-workspace::reminder-browser"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    },
    {
      "unattended": true,
      "when": [
        {
          "entity": "product-settings",
          "fact": "Testing",
          "is": false
        },
        {
          "entity": "product-settings",
          "fact": "Debug",
          "is": false
        }
      ]
    }
  ]
}
---

# Reminder reading permissions

Native Add override checks its source path rather than the ordinary configured model Add permission. Other native operations use actual model checks and own-record queryset and object-view checks. Unattended due changes use the configured sender path

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

The configured sender reads due active records under its non-Testing, non-Debug operating branch; it does not require a human native view permission.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "reminder",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::reminder-record"
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
    }
  ]
}
---

# Reminder creation permissions

Native Add override checks its source path rather than the ordinary configured model Add permission. Other native operations use actual model checks and own-record queryset and object-view checks. Unattended due changes use the configured sender path

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

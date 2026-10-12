---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::user-profile-record"
        },
        {
          "place": "crm-web::crm-workspace::user-profile-browser"
        },
        {
          "place": "crm-web::crm-workspace::task-record"
        },
        {
          "place": "crm-web::crm-workspace::project-record"
        },
        {
          "place": "crm-web::crm-workspace::memo-record"
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

# Account reading permissions

Reads User facts through authorized profile/participant/owner-choice presentation.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

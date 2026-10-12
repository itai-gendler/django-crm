---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-profile",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::user-profile-record"
        },
        {
          "place": "crm-web::crm-workspace::user-profile-browser"
        }
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
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# User profile reading permissions

Ordinary Add forbidden: `permits: []`. Staff-site profile view allowed. Change self or administrator; delete administrator. Automatic profile creation follows the account-creation signal; ordinary profile Add remains forbidden

The actual requesting User must pass active Staff site access. UserProfileAdmin.has_view_permission returns true, including for other and inactive profiles; there is no additional profile model-view or owner test.

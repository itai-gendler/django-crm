---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-profile",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::user-profile-record"
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
  "permits": []
}
---

# User profile creation permissions

Ordinary Add forbidden: `permits: []`. Staff-site profile view allowed. Change self or administrator; delete administrator. Automatic profile creation follows the account-creation signal; ordinary profile Add remains forbidden

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-profile",
      "effect": "changes",
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
  "permits": [
    {
      "actors": [
        "crm-administrator"
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "crm-administrator"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "company-executive"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "sales-manager"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "operator"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "superoperator"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "co-worker"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "task-operator"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "accountant"
        }
      ]
    },
    {
      "related": [
        {
          "verb": "has profile",
          "entity": "user"
        },
        {
          "verb": "has account",
          "entity": "department-head"
        }
      ]
    }
  ]
}
---

# User profile editing permissions

Ordinary Add forbidden: `permits: []`. Staff-site profile view allowed. Change self or administrator; delete administrator. Automatic profile creation follows the account-creation signal; ordinary profile Add remains forbidden

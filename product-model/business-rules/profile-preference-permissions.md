---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user-profile",
      "effect": "changes",
      "facts": [
        "Language",
        "Timezone",
        "Timezone activation",
        "CRM notifications"
      ],
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

# Profile preference permissions

Changes language/timezone/notification preferences; self only, including when an administrator can otherwise edit another Profile.

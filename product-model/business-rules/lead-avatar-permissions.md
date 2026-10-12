---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "lead",
      "effect": "changes",
      "facts": [
        "Avatar"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::lead-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/lead.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-administrator"
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "crm-administrator"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "company-executive"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "sales-manager"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "operator"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "superoperator"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "co-worker"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "task-operator"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "accountant"
        }
      ],
      "configuredBy": "user"
    },
    {
      "related": [
        {
          "verb": "owns",
          "entity": "department-head"
        }
      ],
      "configuredBy": "user"
    }
  ]
}
---

# Lead avatar permissions

Changes Lead avatar; owner or administrator control.

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Every field-control branch also requires successful native change access and actual object lookup; the role/owner grant never bypasses that prerequisite.

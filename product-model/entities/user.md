---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "relations": [
    {
      "entity": "user-profile",
      "verb": "has profile",
      "cardinality": "one-to-one"
    },
    {
      "entity": "user-session",
      "verb": "uses session",
      "cardinality": "one-to-many"
    }
  ]
}
---

# User

Username, name/email, active/staff/superuser status, direct permissions and group memberships; one Profile, multiple Sessions

## Information kept

- **Username** — Account identifier used for authentication and audit display.
- **Name** — The name used to identify the selected record to people.
- **Email address** — Address or address list retained for correspondence and counterparty matching.
- **Active** — Whether this record remains active.
- **Staff** — Whether the account is marked staff for native-site and staff-wrapper access.
- **Superuser** — Whether the account is marked superuser, used by the implemented administrator overrides.
- **Direct permissions** — Model-operation permissions granted directly to this account; effective permission also includes its group configuration.
- **Group memberships** — The account’s configured group memberships; role predicates are derived from them.

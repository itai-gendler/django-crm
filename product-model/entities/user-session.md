---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/usermiddleware.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# User session

Current account, selected department and report display currency; current browser session, not global User selection

## Information kept

- **Current account** — Authenticated account associated with this particular request session.
- **Selected department** — The current session’s selected department, including the all-departments choice where offered.
- **Report currency** — Currency selected for report display in this particular session.

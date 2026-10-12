---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "income-snapshot",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::income-summary"
        },
        {
          "place": "crm-web::crm-workspace::income-snapshot"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/models.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    },
    {
      "unattended": true
    }
  ]
}
---

# Income snapshot creation permissions

Creates snapshots; staff manual handler or unattended monthly capture.

Manual supplied-HTML capture uses the actual requesting User’s active Staff handler wrapper. Unattended monthly capture selects the first Superuser account for an internal authenticated client, fetches the native Income Summary for each manager department and persists only after obtaining the report’s snapshot context. That selected account’s actual site/proxy checks remain prerequisites of the internal fetch; no human initiator or creator identity is fabricated. Testing changes the scheduler’s wait/loop behavior, not a blanket prohibition of capture.

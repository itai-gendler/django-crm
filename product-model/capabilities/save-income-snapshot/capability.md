---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/incomestatadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/utils/monthly_snapshot_saving.py"
    }
  ],
  "domain": "income-summary"
}
---

# Save income snapshot

The supplied report HTML is retained with owner, department and capture information.

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

# View income snapshot

Present income snapshot using the source-specific selection and calculations.

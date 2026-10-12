---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "income-snapshot",
      "effect": "reads",
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
    }
  ]
}
---

# Income snapshot reading permissions

Reads captured HTML; staff handler without an invented department recheck.

The actual requesting User passes the active Staff handler wrapper. It presents the selected retained snapshot without an additional department or snapshot model-view test.

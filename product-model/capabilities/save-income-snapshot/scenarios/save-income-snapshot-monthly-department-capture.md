---
{
  "kind": "primary",
  "routes": {
    "main": "Save income snapshot — monthly department capture"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The configured monthly boundary is reached and department report capture is dispatched.",
      "entities": [
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        }
      ],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-snapshot"
        }
      }
    },
    {
      "kind": "product",
      "text": "The configured monthly boundary captures each department’s report HTML through the synthetic account.",
      "entities": [
        {
          "entity": "income-snapshot",
          "effect": "creates",
          "facts": [
            "HTML",
            "Captured",
            "Owner",
            "Modified by",
            "Department"
          ]
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-snapshot"
        }
      }
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
  ]
}
---

# Save income snapshot — monthly department capture

## Trigger

The configured processing condition occurs.

## Outcome

The configured monthly boundary captures each department’s report HTML through the synthetic account.

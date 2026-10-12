---
{
  "kind": "primary",
  "routes": {
    "main": "Save income snapshot"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the captured financial-report content.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The supplied report HTML is retained with owner, department and capture information.",
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
          "place": "crm-web::crm-workspace::income-summary"
        }
      },
      "actor": "operator"
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

# Save income snapshot

## Trigger

Operator invokes Save income snapshot.

## Outcome

The supplied report HTML is retained with owner, department and capture information.

---
{
  "kind": "primary",
  "routes": {
    "main": "View income snapshot"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Income snapshot and invoke view.",
      "entities": [
        {
          "entity": "income-snapshot",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-snapshot"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected captured report HTML and its department, owner and capture time are presented.",
      "entities": [
        {
          "entity": "income-snapshot",
          "effect": "reads",
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

# View income snapshot

## Trigger

Operator invokes View income snapshot.

## Outcome

The selected captured report HTML and its department, owner and capture time are presented.

---
{
  "kind": "validation",
  "routes": {
    "main": "Edit deal follow up — past next step date"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted changed Deal next-step date precedes today.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke edit.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The changed past next-step date is rejected.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Translation",
            "Amount"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/clarify_permission.py"
    }
  ]
}
---

# Edit deal follow up — past next step date

## Trigger

Operator invokes Edit deal follow up.

## Outcome

The changed past next-step date is rejected.

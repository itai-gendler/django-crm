---
{
  "kind": "primary",
  "routes": {
    "main": "Edit deal — owner updates lead"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Deal’s owner changes while it has a linked Lead.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        },
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
      "text": "The changed Deal owner propagates to its linked Lead.",
      "entities": [
        {
          "entity": "deal",
          "effect": "changes",
          "facts": [
            "Owner"
          ]
        },
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "Owner"
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

# Edit deal — owner updates lead

## Trigger

Operator invokes Edit deal.

## Outcome

The changed Deal owner propagates to its linked Lead.

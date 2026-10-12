---
{
  "kind": "primary",
  "routes": {
    "main": "Remove output"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Output and invoke remove.",
      "entities": [
        {
          "entity": "output",
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
      "text": "The selected output membership is removed from the saved Output. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "output",
          "effect": "removes"
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

# Remove output

## Trigger

Operator invokes Remove output.

## Outcome

The selected output membership is removed from the saved Output. Other retained memberships are preserved.

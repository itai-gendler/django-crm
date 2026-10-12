---
{
  "kind": "primary",
  "routes": {
    "main": "Remove tag"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke remove.",
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
      "text": "The selected CRM Tag is removed from the Deal’s retained tag membership.",
      "entities": [
        {
          "entity": "deal",
          "effect": "changes",
          "facts": [
            "Tags"
          ]
        },
        {
          "entity": "crm-tag",
          "effect": "reads",
          "facts": [
            "Name"
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
      "target": "crm/models/deal.py"
    }
  ]
}
---

# Remove tag

## Trigger

Operator invokes Remove tag.

## Outcome

The selected CRM Tag is removed from the Deal’s retained tag membership.

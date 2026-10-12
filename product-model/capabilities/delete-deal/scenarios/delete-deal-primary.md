---
{
  "kind": "primary",
  "routes": {
    "main": "Delete deal"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke delete.",
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
      "text": "Remove the selected Deal.",
      "entities": [
        {
          "entity": "deal",
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

# Delete deal

## Trigger

Operator invokes Delete deal.

## Outcome

Remove the selected Deal.

---
{
  "kind": "validation",
  "routes": {
    "main": "Remove tag — parent rule refused"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected host or current account fails the corresponding inline/host Rule’s checks.",
      "entities": []
    },
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
      "text": "The attachment/tag mutation is refused.",
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
      "target": "crm/models/deal.py"
    }
  ]
}
---

# Remove tag — parent rule refused

## Trigger

Operator invokes Remove tag.

## Outcome

The attachment/tag mutation is refused.

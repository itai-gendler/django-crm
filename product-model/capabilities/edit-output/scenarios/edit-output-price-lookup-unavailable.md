---
{
  "kind": "edge",
  "routes": {
    "main": "Edit output — price lookup unavailable"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The browser’s price lookup fails for the entered commercial line.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Output and invoke edit.",
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
      "text": "Lookup failure retains the existing/manual amount rather than inventing a replacement.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": [
            "Product",
            "Quantity",
            "Amount",
            "Currency"
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

# Edit output — price lookup unavailable

## Trigger

Operator invokes Edit output.

## Outcome

Lookup failure retains the existing/manual amount rather than inventing a replacement.

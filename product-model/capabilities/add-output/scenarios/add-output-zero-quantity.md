---
{
  "kind": "validation",
  "routes": {
    "main": "Add output — zero quantity"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted Output has quantity zero.",
      "entities": [
        {
          "entity": "output",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Output and invoke add.",
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
      "text": "The Output is not saved with zero quantity.",
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

# Add output — zero quantity

## Trigger

Operator invokes Add output.

## Outcome

The Output is not saved with zero quantity.

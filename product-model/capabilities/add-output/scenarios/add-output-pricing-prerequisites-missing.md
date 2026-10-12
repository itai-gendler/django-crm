---
{
  "kind": "edge",
  "routes": {
    "main": "Add output — pricing prerequisites missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Deal has no existing Outputs and lacks tier name or currency required to expose its inline input.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        },
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
      "text": "Missing pricing prerequisites do not establish a calculated line price.",
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

# Add output — pricing prerequisites missing

## Trigger

Operator invokes Add output.

## Outcome

Missing pricing prerequisites do not establish a calculated line price.

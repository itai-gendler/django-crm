---
{
  "kind": "primary",
  "routes": {
    "main": "Remove request product"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Request and invoke remove.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected request product membership is removed from the saved Request. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Products"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/forms/admin_forms.py"
    }
  ]
}
---

# Remove request product

## Trigger

Operator invokes Remove request product.

## Outcome

The selected request product membership is removed from the saved Request. Other retained memberships are preserved.

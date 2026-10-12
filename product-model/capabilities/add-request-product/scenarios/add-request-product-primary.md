---
{
  "kind": "primary",
  "routes": {
    "main": "Add request product"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Request and invoke add.",
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
      "text": "The selected request product membership is retained on the saved Request. Other retained memberships are preserved.",
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

# Add request product

## Trigger

Operator invokes Add request product.

## Outcome

The selected request product membership is retained on the saved Request. Other retained memberships are preserved.

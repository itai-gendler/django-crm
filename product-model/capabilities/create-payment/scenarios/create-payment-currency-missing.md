---
{
  "kind": "validation",
  "routes": {
    "main": "Create payment — currency missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted Payment has no required currency.",
      "entities": [
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save amount, monetary unit choice, date, status and commercial references.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::payment-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The missing required currency is rejected.",
      "entities": [
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::payment-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/paymentinline.py"
    }
  ]
}
---

# Create payment — currency missing

## Trigger

Operator invokes Create payment.

## Outcome

The missing required currency is rejected.

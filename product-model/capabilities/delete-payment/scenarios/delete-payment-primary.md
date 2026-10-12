---
{
  "kind": "primary",
  "routes": {
    "main": "Delete payment"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Payment and invoke delete.",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::payment-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Remove the selected Payment.",
      "entities": [
        {
          "entity": "payment",
          "effect": "removes"
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

# Delete payment

## Trigger

Operator invokes Delete payment.

## Outcome

Remove the selected Payment.

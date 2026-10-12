---
{
  "kind": "primary",
  "routes": {
    "main": "Edit payment"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Payment and invoke edit.",
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
      "text": "The selected Payment retains the submitted Amount, Currency, Payment date, Status, Contract number, Invoice number, Order number, Through representative. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "payment",
          "effect": "changes",
          "facts": [
            "Amount",
            "Currency",
            "Payment date",
            "Status",
            "Contract number",
            "Invoice number",
            "Order number",
            "Through representative",
            "Deal"
          ]
        },
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

# Edit payment

## Trigger

Operator invokes Edit payment.

## Outcome

The selected Payment retains the submitted Amount, Currency, Payment date, Status, Contract number, Invoice number, Order number, Through representative. Read-only fields retain their previous values and invalid form input returns field errors.

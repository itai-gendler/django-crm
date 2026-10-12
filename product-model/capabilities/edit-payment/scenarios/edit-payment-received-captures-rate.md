---
{
  "kind": "primary",
  "routes": {
    "main": "Edit payment — received captures rate"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Payment is Received and its dated currency conversion is missing.",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
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
      "text": "A missing dated conversion rate is retained for the received Payment.",
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
          "entity": "currency-rate",
          "effect": "creates",
          "facts": [
            "Currency",
            "Date",
            "Conversion values",
            "Rate classification"
          ]
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

# Edit payment — received captures rate

## Trigger

Operator invokes Edit payment.

## Outcome

A missing dated conversion rate is retained for the received Payment.

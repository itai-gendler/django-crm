---
{
  "kind": "primary",
  "routes": {
    "main": "Create payment"
  },
  "steps": [
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
      "text": "A distinct Payment is retained with Amount, Currency, Payment date, Status, Contract number. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "payment",
          "effect": "creates",
          "facts": [
            "Amount",
            "Currency",
            "Payment date",
            "Status",
            "Contract number",
            "Invoice number",
            "Order number",
            "Through representative",
            "Deal",
            "Created",
            "Updated",
            "Modified by"
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

# Create payment

## Trigger

Operator invokes Create payment.

## Outcome

A distinct Payment is retained with Amount, Currency, Payment date, Status, Contract number. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

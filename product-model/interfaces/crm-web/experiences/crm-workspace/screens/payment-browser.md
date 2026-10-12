---
{
  "entities": [
    {
      "entity": "payment",
      "shows": [
        "Amount",
        "Currency",
        "Status",
        "Payment date",
        "Deal"
      ]
    },
    {
      "entity": "currency",
      "shows": [
        "Name",
        "State currency",
        "Marketing currency"
      ]
    },
    {
      "entity": "currency-rate",
      "shows": [
        "Date",
        "Conversion values"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/payment.py"
    }
  ]
}
---

# Payment browser

Deal, amount/currency/date/status, contract/invoice/order references and configured representative option.

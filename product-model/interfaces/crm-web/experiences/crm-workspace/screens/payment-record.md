---
{
  "entities": [
    {
      "entity": "payment",
      "shows": [
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
      ],
      "collects": [
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

# Payment record

Deal, amount/currency/date/status, contract/invoice/order references and configured representative option.

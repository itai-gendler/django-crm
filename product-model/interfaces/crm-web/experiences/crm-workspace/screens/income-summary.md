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
    },
    {
      "entity": "user-session",
      "shows": [
        "Selected department",
        "Report currency"
      ],
      "collects": [
        "Report currency"
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

# Income summary

Received/expected aggregates, period, department, display currency and VAT.

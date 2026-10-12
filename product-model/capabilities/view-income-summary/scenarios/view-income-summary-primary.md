---
{
  "kind": "primary",
  "routes": {
    "main": "View income summary"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Payment and invoke view.",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The source department/period selection presents received and expected financial categories using selected currency, historical-rate fallback and VAT display.",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": [
            "Amount",
            "Currency",
            "Payment date",
            "Status",
            "Contract number",
            "Invoice number",
            "Order number",
            "Through representative"
          ]
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-summary"
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

# View income summary

## Trigger

Operator invokes View income summary.

## Outcome

The source department/period selection presents received and expected financial categories using selected currency, historical-rate fallback and VAT display.

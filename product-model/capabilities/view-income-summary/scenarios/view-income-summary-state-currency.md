---
{
  "kind": "primary",
  "routes": {
    "main": "View income summary — state currency"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current report session selects state-currency presentation.",
      "entities": [
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
      "text": "Income is projected in selected state currency with its own conversion rules.",
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

# View income summary — state currency

## Trigger

Operator invokes View income summary.

## Outcome

Income is projected in selected state currency with its own conversion rules.

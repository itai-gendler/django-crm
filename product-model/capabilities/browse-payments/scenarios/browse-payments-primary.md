---
{
  "kind": "primary",
  "routes": {
    "main": "Browse payments"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Payment and invoke browse.",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::payment-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": [
            "Amount",
            "Currency",
            "Status",
            "Payment date",
            "Deal"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::payment-browser"
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

# Browse payments

## Trigger

Operator invokes Browse payments.

## Outcome

Present the source-defined Payment selection, search/filter results and summary facts.

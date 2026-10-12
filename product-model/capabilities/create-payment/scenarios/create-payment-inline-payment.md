---
{
  "kind": "primary",
  "routes": {
    "main": "Create payment — inline payment"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Deal form includes the inline for an additional financial entry.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save amount, monetary unit choice, date, status and commercial references.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The saved Payment retains the submitted financial and reference facts and its selected Deal association.",
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
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
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

# Create payment — inline payment

## Trigger

Operator invokes Create payment.

## Outcome

The saved Payment retains the submitted financial and reference facts and its selected Deal association.

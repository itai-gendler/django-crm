---
{
  "kind": "primary",
  "routes": {
    "main": "Refresh exchange rates"
  },
  "steps": [
    {
      "kind": "condition",
      "unattended": true,
      "text": "Conversion refresh is due on the configured schedule.",
      "entities": []
    },
    {
      "kind": "product",
      "text": "Refresh enabled conversion information on its configured schedule. Provider failures do not establish fresh rates.",
      "entities": [
        {
          "entity": "currency",
          "effect": "changes",
          "facts": [
            "Current rates",
            "Update date"
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
          "place": "crm-web::crm-workspace::income-summary"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/rates_loader.py"
    }
  ]
}
---

# Refresh exchange rates

## Trigger

The configured processing condition occurs.

## Outcome

Refresh enabled conversion information on its configured schedule. Provider failures do not establish fresh rates.

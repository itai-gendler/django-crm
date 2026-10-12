---
{
  "kind": "edge",
  "routes": {
    "main": "Refresh exchange rates — marketing currency missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "No Currency is configured as the marketing currency needed for refresh.",
      "entities": [
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        }
      ],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "Absent marketing-currency configuration does not establish fresh rates.",
      "entities": [
        {
          "entity": "currency",
          "effect": "reads",
          "facts": [
            "Name",
            "State currency",
            "Marketing currency",
            "Current rates"
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

# Refresh exchange rates — marketing currency missing

## Trigger

The configured processing condition occurs.

## Outcome

Absent marketing-currency configuration does not establish fresh rates.

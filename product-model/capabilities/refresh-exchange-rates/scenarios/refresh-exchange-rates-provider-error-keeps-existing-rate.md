---
{
  "kind": "edge",
  "routes": {
    "main": "Refresh exchange rates — provider error keeps existing rate"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The conversion provider fails before fresh rate information is retained.",
      "entities": [],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::income-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "Provider error retains existing conversion information.",
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

# Refresh exchange rates — provider error keeps existing rate

## Trigger

The configured processing condition occurs.

## Outcome

Provider error retains existing conversion information.

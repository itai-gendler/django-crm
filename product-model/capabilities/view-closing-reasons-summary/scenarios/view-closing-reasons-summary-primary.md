---
{
  "kind": "primary",
  "routes": {
    "main": "View closing reasons summary"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke view.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::closing-reasons-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The closing projection presents grouped Deal outcomes by closing reason.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Translation",
            "Amount",
            "Currency",
            "Tier name",
            "Discount type",
            "Discount"
          ]
        },
        {
          "entity": "closing-reason",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::closing-reasons-summary"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/closingreasonstatadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View closing reasons summary

## Trigger

Operator invokes View closing reasons summary.

## Outcome

The closing projection presents grouped Deal outcomes by closing reason.

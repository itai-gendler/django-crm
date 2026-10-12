---
{
  "kind": "primary",
  "routes": {
    "main": "View deals summary"
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
          "place": "crm-web::crm-workspace::deals-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Deal projection presents its closed/successful totals under this report’s activity, successful-reason and closing-date criteria.",
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
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deals-summary"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/dealstatadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View deals summary

## Trigger

Operator invokes View deals summary.

## Outcome

The Deal projection presents its closed/successful totals under this report’s activity, successful-reason and closing-date criteria.

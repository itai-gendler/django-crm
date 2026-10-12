---
{
  "kind": "primary",
  "routes": {
    "main": "View sales funnel"
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
          "place": "crm-web::crm-workspace::sales-funnel"
        }
      }
    },
    {
      "kind": "product",
      "text": "Closed relevant Deals are grouped by their current stage; historical traversal and a live active pipeline are not inferred.",
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
          "place": "crm-web::crm-workspace::sales-funnel"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/salesfunnelsadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View sales funnel

## Trigger

Operator invokes View sales funnel.

## Outcome

Closed relevant Deals are grouped by their current stage; historical traversal and a live active pipeline are not inferred.

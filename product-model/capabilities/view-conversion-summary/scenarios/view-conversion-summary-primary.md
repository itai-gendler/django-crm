---
{
  "kind": "primary",
  "routes": {
    "main": "View conversion summary"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Request and invoke view.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::conversion-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Request/Deal projection presents its conversion totals using this report’s successful and conditionally successful stage criteria.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": [
            "Subject",
            "Description",
            "Remark",
            "Translation",
            "Person name",
            "Email address",
            "Telephone",
            "Company name"
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
          "place": "crm-web::crm-workspace::conversion-summary"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/conversionadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View conversion summary

## Trigger

Operator invokes View conversion summary.

## Outcome

The Request/Deal projection presents its conversion totals using this report’s successful and conditionally successful stage criteria.

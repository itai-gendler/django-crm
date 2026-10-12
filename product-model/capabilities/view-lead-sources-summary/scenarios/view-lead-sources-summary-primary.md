---
{
  "kind": "primary",
  "routes": {
    "main": "View lead sources summary"
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
          "place": "crm-web::crm-workspace::lead-sources-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The source-attribution projection presents selected source totals.",
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
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-sources-summary"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/leadsourcestatadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View lead sources summary

## Trigger

Operator invokes View lead sources summary.

## Outcome

The source-attribution projection presents selected source totals.

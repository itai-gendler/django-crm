---
{
  "kind": "primary",
  "routes": {
    "main": "View requests summary"
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
          "place": "crm-web::crm-workspace::requests-summary"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected inquiry projection applies duplicate, case and disqualified-source exclusions and presents its counts.",
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
          "place": "crm-web::crm-workspace::requests-summary"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/requeststatadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "analytics/site/anlmodeladmin.py"
    }
  ]
}
---

# View requests summary

## Trigger

Operator invokes View requests summary.

## Outcome

The selected inquiry projection applies duplicate, case and disqualified-source exclusions and presents its counts.

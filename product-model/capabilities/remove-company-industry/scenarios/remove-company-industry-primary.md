---
{
  "kind": "primary",
  "routes": {
    "main": "Remove company industry"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Company and invoke remove.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected company industry membership is removed from the saved Company. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "company",
          "effect": "changes",
          "facts": [
            "Industries"
          ]
        },
        {
          "entity": "industry",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
    }
  ]
}
---

# Remove company industry

## Trigger

Operator invokes Remove company industry.

## Outcome

The selected company industry membership is removed from the saved Company. Other retained memberships are preserved.

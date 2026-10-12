---
{
  "kind": "primary",
  "routes": {
    "main": "Add company industry"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Company and invoke add.",
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
      "text": "The selected company industry membership is retained on the saved Company. Other retained memberships are preserved.",
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

# Add company industry

## Trigger

Operator invokes Add company industry.

## Outcome

The selected company industry membership is retained on the saved Company. Other retained memberships are preserved.

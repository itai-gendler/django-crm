---
{
  "kind": "primary",
  "routes": {
    "main": "Browse companies — search replaces scope"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "A nonempty Company search reaches CompanyAdmin’s replacement-queryset branch.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Company and invoke browse.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Company search branch uses the replacement queryset.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [
            "Full name",
            "Client types",
            "Created",
            "Owner",
            "Mailing eligibility",
            "Registration number"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
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

# Browse companies — search replaces scope

## Trigger

Operator invokes Browse companies.

## Outcome

The Company search branch uses the replacement queryset.

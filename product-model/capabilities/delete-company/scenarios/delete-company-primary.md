---
{
  "kind": "primary",
  "routes": {
    "main": "Delete company"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Company and invoke delete.",
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
      "text": "Remove the selected Company.",
      "entities": [
        {
          "entity": "company",
          "effect": "removes"
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

# Delete company

## Trigger

Operator invokes Delete company.

## Outcome

Remove the selected Company.

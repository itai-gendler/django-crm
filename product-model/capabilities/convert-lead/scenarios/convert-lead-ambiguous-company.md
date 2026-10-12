---
{
  "kind": "validation",
  "routes": {
    "main": "Convert lead — ambiguous company"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Conversion finds multiple corporate matches rather than a unique Company.",
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
      "text": "Invoke the offered convert control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "actor": "operator",
      "text": "The Product saves the edited Lead contact and corporate information before resolving conversion targets.",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "First name",
            "Last name",
            "Company name",
            "Email address",
            "Telephone",
            "Country",
            "City",
            "Company",
            "Contact person"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The ambiguous Company result is reported without a unique match assertion.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Avatar"
          ]
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    }
  ]
}
---

# Convert lead — ambiguous company

## Trigger

Operator invokes Convert lead.

## Outcome

The ambiguous Company result is reported without a unique match assertion.

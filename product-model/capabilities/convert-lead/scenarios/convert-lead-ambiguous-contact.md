---
{
  "kind": "validation",
  "routes": {
    "main": "Convert lead — ambiguous contact"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Conversion finds multiple matching Contact persons rather than a unique selection.",
      "entities": [
        {
          "entity": "contact-person",
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
      "text": "The ambiguous Contact result is reported without a unique match assertion.",
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

# Convert lead — ambiguous contact

## Trigger

Operator invokes Convert lead.

## Outcome

The ambiguous Contact result is reported without a unique match assertion.

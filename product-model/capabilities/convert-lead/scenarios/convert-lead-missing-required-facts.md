---
{
  "kind": "validation",
  "routes": {
    "main": "Convert lead — missing required facts"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Conversion input lacks the required corporate or personal contact information.",
      "entities": []
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
      "text": "Missing conversion facts are reported and conversion is not completed.",
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

# Convert lead — missing required facts

## Trigger

Operator invokes Convert lead.

## Outcome

Missing conversion facts are reported and conversion is not completed.

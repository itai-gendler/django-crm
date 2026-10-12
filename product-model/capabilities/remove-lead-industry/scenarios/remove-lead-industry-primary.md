---
{
  "kind": "primary",
  "routes": {
    "main": "Remove lead industry"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Lead and invoke remove.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
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
      "text": "The selected lead industry membership is removed from the saved Lead. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "lead",
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

# Remove lead industry

## Trigger

Operator invokes Remove lead industry.

## Outcome

The selected lead industry membership is removed from the saved Lead. Other retained memberships are preserved.

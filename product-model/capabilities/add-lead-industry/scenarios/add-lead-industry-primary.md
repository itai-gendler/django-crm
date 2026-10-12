---
{
  "kind": "primary",
  "routes": {
    "main": "Add lead industry"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Lead and invoke add.",
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
      "text": "The selected lead industry membership is retained on the saved Lead. Other retained memberships are preserved.",
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

# Add lead industry

## Trigger

Operator invokes Add lead industry.

## Outcome

The selected lead industry membership is retained on the saved Lead. Other retained memberships are preserved.

---
{
  "kind": "primary",
  "routes": {
    "main": "Request callback — multiple connections"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current account has more than one active owned Connection.",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Initiate a call using the offered owned telephone setup.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::callback"
        }
      }
    },
    {
      "kind": "product",
      "text": "The user selects an active owned connection before callback.",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Owner",
            "Active",
            "Provider",
            "Caller identity",
            "Number"
          ]
        },
        {
          "entity": "user",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::callback"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "voip/views/callback.py"
    }
  ]
}
---

# Request callback — multiple connections

## Trigger

Operator invokes Request callback.

## Outcome

The user selects an active owned connection before callback.

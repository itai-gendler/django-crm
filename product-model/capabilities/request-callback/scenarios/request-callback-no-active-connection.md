---
{
  "kind": "edge",
  "routes": {
    "main": "Request callback — no active connection"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current account has no active owned Connection.",
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
      "text": "Missing-connection information returns without callback.",
      "entities": [
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Owner",
            "Active",
            "Provider",
            "Caller identity"
          ]
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

# Request callback — no active connection

## Trigger

Operator invokes Request callback.

## Outcome

Missing-connection information returns without callback.

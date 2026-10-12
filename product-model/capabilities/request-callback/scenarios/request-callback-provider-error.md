---
{
  "kind": "edge",
  "routes": {
    "main": "Request callback — provider error"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The callback provider returns its failure result.",
      "entities": []
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
      "text": "The callback provider failure is presented.",
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

# Request callback — provider error

## Trigger

Operator invokes Request callback.

## Outcome

The callback provider failure is presented.

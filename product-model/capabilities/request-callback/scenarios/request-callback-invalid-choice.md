---
{
  "kind": "validation",
  "routes": {
    "main": "Request callback — invalid choice"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The callback submits a connection outside the available active owned choices.",
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
      "text": "The connection choice is rejected.",
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

# Request callback — invalid choice

## Trigger

Operator invokes Request callback.

## Outcome

The connection choice is rejected.

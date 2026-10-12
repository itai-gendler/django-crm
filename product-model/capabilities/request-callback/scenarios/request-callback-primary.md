---
{
  "kind": "primary",
  "routes": {
    "main": "Request callback"
  },
  "steps": [
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
      "text": "The sole active owned connection initiates the provider callback and its returned result is presented.",
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

# Request callback

## Trigger

Operator invokes Request callback.

## Outcome

The sole active owned connection initiates the provider callback and its returned result is presented.

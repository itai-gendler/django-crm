---
{
  "kind": "primary",
  "routes": {
    "main": "Receive pbx notification — challenge"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The PBX request supplies its challenge parameter.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "zadarma-pbx"
    },
    {
      "kind": "actor",
      "actor": "zadarma-pbx",
      "text": "Submit the provider challenge or notification payload.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "zadarma-notifications"
        }
      }
    },
    {
      "kind": "product",
      "text": "The provider challenge is echoed without a call update.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "zadarma-notifications"
        }
      },
      "actor": "zadarma-pbx"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "voip/views/voipwebhook.py"
    }
  ]
}
---

# Receive pbx notification — challenge

## Trigger

Zadarma PBX invokes Receive pbx notification.

## Outcome

The provider challenge is echoed without a call update.

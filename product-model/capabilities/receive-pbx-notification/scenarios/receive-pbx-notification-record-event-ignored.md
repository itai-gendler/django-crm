---
{
  "kind": "primary",
  "routes": {
    "main": "Receive pbx notification — record event ignored"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The PBX event is its recording notification, which the handler acknowledges without call processing.",
      "entities": []
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
      "text": "Record event is acknowledged without a Call Entity or workflow update.",
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

# Receive pbx notification — record event ignored

## Trigger

Zadarma PBX invokes Receive pbx notification.

## Outcome

Record event is acknowledged without a Call Entity or workflow update.

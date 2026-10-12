---
{
  "kind": "edge",
  "routes": {
    "main": "Receive pbx notification — unmatched forward"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The validated call has no matched CRM person and the unmatched-forward destination is configured.",
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
      "text": "The unmatched event is forwarded where configured without inventing a matched CRM subject.",
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

# Receive pbx notification — unmatched forward

## Trigger

Zadarma PBX invokes Receive pbx notification.

## Outcome

The unmatched event is forwarded where configured without inventing a matched CRM subject.

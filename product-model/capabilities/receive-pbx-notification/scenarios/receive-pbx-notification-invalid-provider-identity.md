---
{
  "kind": "validation",
  "routes": {
    "main": "Receive pbx notification — invalid provider identity"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The call notification fails its source IP or HMAC identity validation.",
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
      "text": "Invalid provider IP/signature is rejected without a call update.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Birth date"
          ]
        },
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
        }
      ],
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

# Receive pbx notification — invalid provider identity

## Trigger

Zadarma PBX invokes Receive pbx notification.

## Outcome

Invalid provider IP/signature is rejected without a call update.

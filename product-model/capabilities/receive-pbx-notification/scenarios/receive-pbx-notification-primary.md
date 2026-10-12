---
{
  "kind": "primary",
  "routes": {
    "main": "Receive pbx notification"
  },
  "steps": [
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
      "text": "A validated supported incoming call matches telephone information, updates Contact/Lead last-contact time and the selected recent active Deal’s workflow.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "changes",
          "facts": [
            "Last contact"
          ]
        },
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "Last contact"
          ]
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Active",
            "Updated"
          ]
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

# Receive pbx notification

## Trigger

Zadarma PBX invokes Receive pbx notification.

## Outcome

A validated supported incoming call matches telephone information, updates Contact/Lead last-contact time and the selected recent active Deal’s workflow.

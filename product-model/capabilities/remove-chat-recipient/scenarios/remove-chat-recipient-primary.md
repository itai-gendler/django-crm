---
{
  "kind": "primary",
  "routes": {
    "main": "Remove chat recipient"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Chat message and invoke remove.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected chat recipient membership is removed from the saved Chat message. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "changes",
          "facts": [
            "Audience",
            "Unread recipients"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      },
      "actor": "co-worker"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "chat/site/chatmessageadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "chat/forms/chatmessageform.py"
    }
  ]
}
---

# Remove chat recipient

## Trigger

Co worker invokes Remove chat recipient.

## Outcome

The selected chat recipient membership is removed from the saved Chat message. Other retained memberships are preserved.

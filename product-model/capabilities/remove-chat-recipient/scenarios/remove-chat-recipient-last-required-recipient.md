---
{
  "kind": "validation",
  "routes": {
    "main": "Remove chat recipient — last required recipient"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The proposed chat audience would be empty after removing its final member.",
      "entities": []
    },
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
      "text": "Removal of the required final audience member is rejected.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Audience"
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

# Remove chat recipient — last required recipient

## Trigger

Co worker invokes Remove chat recipient.

## Outcome

Removal of the required final audience member is rejected.

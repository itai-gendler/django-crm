---
{
  "kind": "primary",
  "routes": {
    "main": "Edit chat message"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Chat message and invoke edit.",
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
      "text": "The saved contribution retains the submitted content, audience, reply and related-subject information; its author becomes the current editor and its creation time is preserved.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "changes",
          "facts": [
            "Content",
            "Author",
            "Audience",
            "Unread recipients",
            "Reply",
            "Related subject"
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

# Edit chat message

## Trigger

Co worker invokes Edit chat message.

## Outcome

The saved contribution retains the submitted content, audience, reply and related-subject information; its author becomes the current editor and its creation time is preserved.

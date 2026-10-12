---
{
  "kind": "primary",
  "routes": {
    "main": "Reply chat message"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Chat message and invoke reply.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "reads",
          "facts": [],
          "as": "original-message"
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
      "text": "The Product saves a distinct reply with the selected audience and current author, acknowledges the original message and returns to the conversation browser.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Author",
            "Audience",
            "Unread recipients",
            "Date",
            "Reply",
            "Related subject"
          ],
          "as": "reply-message"
        },
        {
          "entity": "chat-message",
          "as": "original-message",
          "effect": "changes",
          "facts": [
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

# Reply chat message

## Trigger

Co worker invokes Reply chat message.

## Outcome

The reply retains the source conversation and related subject, addresses the prior author and creates a new Chat message before returning to the conversation browser.

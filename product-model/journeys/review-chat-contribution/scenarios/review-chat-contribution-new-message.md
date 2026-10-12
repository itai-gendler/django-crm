---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Save a contribution with its intended audience.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      },
      "capability": "create-chat-message"
    },
    {
      "kind": "product",
      "text": "A distinct Chat message is retained with Subject, Content, Author, Audience, Unread recipients. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
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
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      },
      "actor": "co-worker",
      "capability": "create-chat-message"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "create-chat-message",
      "text": "The Product opens the conversation browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Chat message and invoke browse.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-browser"
        }
      },
      "capability": "browse-chat-messages"
    },
    {
      "kind": "product",
      "text": "Present the source-defined Chat message selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "changes",
          "facts": [
            "Unread recipients"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-browser"
        }
      },
      "actor": "co-worker",
      "capability": "browse-chat-messages"
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

# Review chat contribution — new message

## Trigger

The co worker starts by save a contribution with its intended audience.

## Outcome

The participant creates, edits or replies to a contribution, reaches its related conversation browser and inspects the retained message. Viewing acknowledges the current account’s unread membership; replies are distinct records.

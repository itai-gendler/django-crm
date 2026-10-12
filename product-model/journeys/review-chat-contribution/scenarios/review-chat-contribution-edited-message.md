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
      },
      "capability": "edit-chat-message"
    },
    {
      "kind": "product",
      "text": "The contribution retains its edited content and audience; the current editor becomes its author.",
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
      "actor": "co-worker",
      "capability": "edit-chat-message"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "edit-chat-message",
      "text": "The saved contribution returns to the conversation browser.",
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

# Review chat contribution — edited message

## Trigger

The co worker starts by select Chat message and invoke edit.

## Outcome

The participant creates, edits or replies to a contribution, reaches its related conversation browser and inspects the retained message. Viewing acknowledges the current account’s unread membership; replies are distinct records.

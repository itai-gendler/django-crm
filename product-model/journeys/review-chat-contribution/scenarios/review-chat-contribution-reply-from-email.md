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
      },
      "capability": "reply-chat-message"
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
      "actor": "co-worker",
      "capability": "reply-chat-message"
    },
    {
      "kind": "product",
      "actor": "co-worker",
      "capability": "reply-chat-message",
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
          "facts": [],
          "as": "reply-message"
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
          ],
          "as": "reply-message"
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

# Review chat contribution — reply from email

## Trigger

The co worker starts by select Chat message and invoke reply.

## Outcome

The participant creates, edits or replies to a contribution, reaches its related conversation browser and inspects the retained message. Viewing acknowledges the current account’s unread membership; replies are distinct records.

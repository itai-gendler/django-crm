---
{
  "kind": "primary",
  "routes": {
    "main": "Create chat message"
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
      }
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

# Create chat message

## Trigger

Co worker invokes Create chat message.

## Outcome

A distinct Chat message is retained with Subject, Content, Author, Audience, Unread recipients. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

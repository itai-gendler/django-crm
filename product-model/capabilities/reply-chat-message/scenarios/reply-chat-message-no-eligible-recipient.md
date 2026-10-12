---
{
  "kind": "edge",
  "routes": {
    "main": "Reply chat message — no eligible recipient"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The reply’s source-derived audience contains no usable selection.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "co-worker",
      "text": "Select Chat message and invoke reply.",
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
      "text": "No eligible reply audience is reported without saving an empty-audience contribution.",
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

# Reply chat message — no eligible recipient

## Trigger

Co worker invokes Reply chat message.

## Outcome

No eligible reply audience is reported without saving an empty-audience contribution.

---
{
  "kind": "primary",
  "routes": {
    "main": "Attach file — chat"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The upload is attached to the selected Chat message.",
      "entities": [
        {
          "entity": "chat-message",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the attachment for the selected subject.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      }
    },
    {
      "kind": "product",
      "text": "The attachment belongs to the selected Chat message.",
      "entities": [
        {
          "entity": "file",
          "effect": "creates",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ]
        },
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
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/get_file_links.py"
    }
  ]
}
---

# Attach file — chat

## Trigger

Operator invokes Attach file.

## Outcome

The attachment belongs to the selected Chat message.

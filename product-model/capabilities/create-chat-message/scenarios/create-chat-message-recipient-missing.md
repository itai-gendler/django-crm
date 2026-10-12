---
{
  "kind": "validation",
  "routes": {
    "main": "Create chat message — recipient missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted chat contribution has an empty required audience.",
      "entities": []
    },
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
      "text": "The missing required chat audience is rejected.",
      "entities": [],
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

# Create chat message — recipient missing

## Trigger

Co worker invokes Create chat message.

## Outcome

The missing required chat audience is rejected.

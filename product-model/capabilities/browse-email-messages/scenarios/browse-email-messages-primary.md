---
{
  "kind": "primary",
  "routes": {
    "main": "Browse Email messages"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Email Message and invoke browse.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Owner",
            "Updated"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-browser"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/emlmessageadmin.py"
    }
  ]
}
---

# Browse Email messages

## Trigger

Sales manager invokes Browse Email messages.

## Outcome

Present the source-defined Email Message selection, search/filter results and summary facts.

---
{
  "kind": "edge",
  "routes": {
    "main": "Download original Email — fetch error"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Remote original-message fetching fails on the download path.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Invoke the offered download control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Original download returns its fetch failure instead of a file.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To"
          ]
        },
        {
          "entity": "file",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Download original Email — fetch error

## Trigger

Operator invokes Download original Email.

## Outcome

Original download returns its fetch failure instead of a file.

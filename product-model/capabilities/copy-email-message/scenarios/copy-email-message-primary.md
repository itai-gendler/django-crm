---
{
  "kind": "primary",
  "routes": {
    "main": "Copy Email message"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Invoke the saved reusable-content copy control.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content"
          ],
          "as": "source-content"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct saved reusable message copies content, uses the acting account’s default signature or none, assigns the current owner, and opens in its editor.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Signature",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ],
          "as": "copied-content"
        },
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/copy_message.py"
    }
  ]
}
---

# Copy Email message

## Trigger

Sales manager invokes Copy Email message.

## Outcome

A distinct saved reusable message copies content, uses the acting account’s default signature or none, assigns the current owner, and opens in its editor.

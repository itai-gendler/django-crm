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
      },
      "capability": "copy-email-message"
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
      "actor": "sales-manager",
      "capability": "copy-email-message"
    },
    {
      "kind": "product",
      "actor": "sales-manager",
      "capability": "copy-email-message",
      "text": "The Product opens the saved reusable-content copy editor for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Email Message and invoke edit.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "reads",
          "facts": [],
          "as": "copied-content"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-message-record"
        }
      },
      "capability": "edit-email-message"
    },
    {
      "kind": "product",
      "text": "The selected Email Message retains the submitted Subject, Content, Signature. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "email-message",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content",
            "Signature",
            "Department"
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
          "place": "crm-web::crm-workspace::email-message-record"
        }
      },
      "actor": "sales-manager",
      "capability": "edit-email-message"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/copy_message.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/emlmessageadmin.py"
    }
  ]
}
---

# Edit copied email message — saved copy

## Trigger

The sales manager starts by invoke the saved reusable-content copy control.

## Outcome

The selected Email Message retains the submitted Subject, Content, Signature. Read-only fields retain their previous values and invalid form input returns field errors.

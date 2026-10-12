---
{
  "kind": "primary",
  "routes": {
    "main": "Create linked Email — linked deal"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The helper is invoked for the selected Deal without a submitted attachment selection.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Compose correspondence for the linked commercial subject.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The helper opens the unsaved correspondence Add form with source addresses, relation, ticket and signing defaults; this GET persists no draft.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      },
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the prepared correspondence through native Add.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The native Add save retains a distinct Email in CRM with the submitted linked correspondence and source defaults.",
      "entities": [
        {
          "entity": "email",
          "effect": "creates",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To",
            "CC",
            "BCC",
            "Signature",
            "Date",
            "Ticket",
            "Message identity",
            "Mailbox UID",
            "Email account",
            "Incoming",
            "Sent",
            "Trash",
            "Company",
            "Contact person",
            "Lead",
            "Deal",
            "Request",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "deal",
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
      "target": "crm/views/create_email.py"
    }
  ]
}
---

# Create linked Email — linked deal

## Trigger

Operator invokes Create linked Email.

## Outcome

The native Add save retains a distinct Email in CRM with the submitted linked correspondence and source defaults.

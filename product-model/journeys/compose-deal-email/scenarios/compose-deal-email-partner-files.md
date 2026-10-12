---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Deal has files and the actor submits an attachment selection for its correspondence.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "file",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator",
      "capability": "create-linked-email"
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
      },
      "capability": "create-linked-email"
    },
    {
      "kind": "product",
      "text": "Selected Deal file references belong to the saved draft opened in its editor.",
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
          "entity": "file",
          "effect": "creates",
          "with": "email",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
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
          "place": "crm-web::crm-workspace"
        }
      },
      "actor": "operator",
      "capability": "create-linked-email"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "create-linked-email",
      "text": "The Product opens the created correspondence editor for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke edit.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "capability": "edit-email"
    },
    {
      "kind": "product",
      "text": "The outgoing correspondence retains the submitted subject, content, recipient addresses, signature and related-subject fields exposed in its editor. Sender and creation date remain presentation/default facts; the save retains modifying account and update time.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content",
            "To",
            "CC",
            "BCC",
            "Signature",
            "Company",
            "Contact person",
            "Lead",
            "Deal",
            "Request",
            "Modified by",
            "Updated"
          ]
        },
        {
          "entity": "signature",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator",
      "capability": "edit-email"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "edit-email",
      "text": "The Product opens the send control of that saved correspondence for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke send.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "capability": "send-email"
    },
    {
      "kind": "product",
      "text": "SMTP processing returns normally through the correspondence owner's main account. Sent is persisted and the Email browser opens. This records accepted processing, not recipient delivery.",
      "entities": [
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Sent"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator",
      "capability": "send-email"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/create_email.py"
    },
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

# Compose deal email — partner files

## Trigger

The operator starts by compose correspondence for the linked commercial subject.

## Outcome

SMTP processing returns normally through the Email owner's main account. The linked Deal receives its workflow entry when present, Sent is persisted and the Email browser opens. This records accepted processing, not recipient delivery.

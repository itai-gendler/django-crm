---
{
  "kind": "primary",
  "routes": {
    "main": "Retry failed recipients"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Mailing Out and invoke retry.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Failed recipient IDs are returned to the pending campaign queue, the failure list and failed count are cleared, and queued count is updated.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "changes",
          "facts": [
            "Pending recipients",
            "Failed recipients",
            "Status"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/admin_actions.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/utils/sendmassmail.py"
    }
  ]
}
---

# Retry failed recipients

## Trigger

Sales manager invokes Retry failed recipients.

## Outcome

Failed recipient IDs are returned to the pending campaign queue, the failure list and failed count are cleared, and queued count is updated.

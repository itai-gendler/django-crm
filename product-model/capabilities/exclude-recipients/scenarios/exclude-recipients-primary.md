---
{
  "kind": "primary",
  "routes": {
    "main": "Exclude recipients"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Mailing Out and invoke exclude.",
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
      "text": "The selected recipient IDs are removed from the pending campaign queue and retained in its exclusion list; the excluded count is updated.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "changes",
          "facts": [
            "Pending recipients",
            "Recipient count"
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

# Exclude recipients

## Trigger

Sales manager invokes Exclude recipients.

## Outcome

The selected recipient IDs are removed from the pending campaign queue and retained in its exclusion list; the excluded count is updated.

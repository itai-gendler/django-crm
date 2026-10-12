---
{
  "kind": "primary",
  "routes": {
    "main": "Browse mailing outs"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Mailing Out and invoke browse.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Present the source-defined Mailing Out selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": [
            "Name",
            "Message",
            "Recipient type",
            "Status",
            "Pending recipients",
            "Successful recipients",
            "Failed recipients",
            "Recipient count"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-browser"
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

# Browse mailing outs

## Trigger

Sales manager invokes Browse mailing outs.

## Outcome

Present the source-defined Mailing Out selection, search/filter results and summary facts.

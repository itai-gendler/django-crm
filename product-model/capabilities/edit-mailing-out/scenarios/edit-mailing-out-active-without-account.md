---
{
  "kind": "validation",
  "routes": {
    "main": "Edit mailing out — active without account"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The campaign is submitted as Active without its required sending account.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Mailing Out and invoke edit.",
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
      "text": "Missing account returns attempted activation to Paused with a warning.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": [
            "Name",
            "Message",
            "Recipient type",
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

# Edit mailing out — active without account

## Trigger

Sales manager invokes Edit mailing out.

## Outcome

Missing account returns attempted activation to Paused with a warning.

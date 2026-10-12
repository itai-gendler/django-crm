---
{
  "kind": "primary",
  "routes": {
    "main": "Delete mailing out"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Select Mailing Out and invoke delete.",
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
      "text": "Remove the selected Mailing Out.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "removes"
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

# Delete mailing out

## Trigger

Sales manager invokes Delete mailing out.

## Outcome

Remove the selected Mailing Out.

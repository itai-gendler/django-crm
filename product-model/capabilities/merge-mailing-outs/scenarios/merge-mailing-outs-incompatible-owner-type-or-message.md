---
{
  "kind": "validation",
  "routes": {
    "main": "Merge mailing outs — incompatible owner type or message"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected campaigns differ in owner, recipient type or reusable message.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Invoke the offered merge control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Incompatible campaigns remain unmerged.",
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

# Merge mailing outs — incompatible owner type or message

## Trigger

Sales manager invokes Merge mailing outs.

## Outcome

Incompatible campaigns remain unmerged.

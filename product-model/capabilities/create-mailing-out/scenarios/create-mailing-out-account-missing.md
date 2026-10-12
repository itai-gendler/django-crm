---
{
  "kind": "edge",
  "routes": {
    "main": "Create mailing out — account missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "No usable account exists for this operation; sending uses the correspondence owner’s main account.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Submit the eligible newsletter audience selection.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Missing account is reported and the send/import/campaign operation is not completed.",
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
          "place": "crm-web::crm-workspace::company-browser"
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

# Create mailing out — account missing

## Trigger

Sales manager invokes Create mailing out.

## Outcome

Missing account is reported and the send/import/campaign operation is not completed.

---
{
  "kind": "edge",
  "routes": {
    "main": "Create mailing out — no eligible recipients"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The campaign selection contains no recipient passing its mailing eligibility checks.",
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
      "text": "No eligible recipient is reported and no accepted campaign is created.",
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

# Create mailing out — no eligible recipients

## Trigger

Sales manager invokes Create mailing out.

## Outcome

No eligible recipient is reported and no accepted campaign is created.

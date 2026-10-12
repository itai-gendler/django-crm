---
{
  "kind": "validation",
  "routes": {
    "main": "Create mailing out — mixed owners"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparties belong to different owners.",
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
      "text": "The mixed-owner selection is rejected.",
      "entities": [],
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

# Create mailing out — mixed owners

## Trigger

Sales manager invokes Create mailing out.

## Outcome

The mixed-owner selection is rejected.

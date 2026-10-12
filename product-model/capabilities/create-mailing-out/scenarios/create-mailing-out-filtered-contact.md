---
{
  "kind": "primary",
  "routes": {
    "main": "Create mailing out — filtered contact"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The filtered Contact person selection is passed to campaign creation with its actual owner filter.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Submit the eligible newsletter audience selection.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
        }
      }
    },
    {
      "kind": "product",
      "text": "The campaign uses the filtered Contact selection and actual owner filter.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "creates",
          "facts": [
            "Name",
            "Message",
            "Recipient type",
            "Status",
            "Pending recipients",
            "Successful recipients",
            "Failed recipients",
            "Recipient count",
            "Successful count",
            "Failed count",
            "Daily count",
            "Sending date",
            "Report",
            "Email account",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace"
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

# Create mailing out — filtered contact

## Trigger

Sales manager invokes Create mailing out.

## Outcome

The campaign uses the filtered Contact selection and actual owner filter.

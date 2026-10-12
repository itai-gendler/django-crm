---
{
  "kind": "primary",
  "routes": {
    "main": "Create mailing out"
  },
  "steps": [
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
      "text": "A paused Mailing Out is retained from the eligible selected Company audience, with its message, recipient type and queues, then opens for editing.",
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
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
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

# Create mailing out

## Trigger

Sales manager invokes Create mailing out.

## Outcome

A paused Mailing Out is retained from the eligible selected Company audience, with its message, recipient type and queues, then opens for editing.

---
{
  "kind": "primary",
  "routes": {
    "main": "Create mailing out — selected contact"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The campaign selection consists of Contact persons.",
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
          "place": "crm-web::crm-workspace::contact-person-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The campaign queue uses selected Contact persons.",
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
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
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

# Create mailing out — selected contact

## Trigger

Sales manager invokes Create mailing out.

## Outcome

The campaign queue uses selected Contact persons.

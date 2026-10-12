---
{
  "kind": "primary",
  "routes": {
    "main": "Edit deal"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke edit.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected Deal retains the submitted Name, Description, Translation, Amount, Currency, Tier name, Discount type, Discount. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "deal",
          "effect": "changes",
          "facts": [
            "Name",
            "Description",
            "Translation",
            "Amount",
            "Currency",
            "Tier name",
            "Discount type",
            "Discount",
            "Stage",
            "Stage dates",
            "Active",
            "Relevant",
            "Important",
            "New",
            "Closing reason",
            "Closing date",
            "Successful closing date",
            "Next step",
            "Next step date",
            "Reminder",
            "Department",
            "Request",
            "Company",
            "Contact person",
            "Lead",
            "Partner contact",
            "Ticket"
          ]
        },
        {
          "entity": "currency",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/clarify_permission.py"
    }
  ]
}
---

# Edit deal

## Trigger

Operator invokes Edit deal.

## Outcome

The selected Deal retains the submitted Name, Description, Translation, Amount, Currency, Tier name, Discount type, Discount. Read-only fields retain their previous values and invalid form input returns field errors.

---
{
  "kind": "primary",
  "routes": {
    "main": "Edit deal — unsuccessful close"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Deal has received and nonreceived Payments and is closed with an unsuccessful reason.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
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
      "text": "The unsuccessful reason closes the Deal and removes nonreceived Payments, preserving received Payments.",
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
          "entity": "payment",
          "effect": "removes"
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

# Edit deal — unsuccessful close

## Trigger

Operator invokes Edit deal.

## Outcome

The unsuccessful reason closes the Deal and removes nonreceived Payments, preserving received Payments.

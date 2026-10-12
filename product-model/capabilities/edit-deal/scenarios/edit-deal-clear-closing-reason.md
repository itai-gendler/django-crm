---
{
  "kind": "primary",
  "routes": {
    "main": "Edit deal — clear closing reason"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Deal has a closing reason and the editor clears it.",
      "entities": [
        {
          "entity": "closing-reason",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "deal",
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
      "text": "Clearing the reason reactivates and clears closing date while retaining recorded successful-closing time.",
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

# Edit deal — clear closing reason

## Trigger

Operator invokes Edit deal.

## Outcome

Clearing the reason reactivates and clears closing date while retaining recorded successful-closing time.

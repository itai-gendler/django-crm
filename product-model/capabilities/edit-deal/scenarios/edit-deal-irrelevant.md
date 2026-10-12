---
{
  "kind": "primary",
  "routes": {
    "main": "Edit deal — irrelevant"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The editor clears the Deal’s Relevant choice.",
      "entities": [
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
      "text": "Marking irrelevant makes the Deal inactive and sets closing date.",
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

# Edit deal — irrelevant

## Trigger

Operator invokes Edit deal.

## Outcome

Marking irrelevant makes the Deal inactive and sets closing date.

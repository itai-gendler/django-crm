---
{
  "kind": "primary",
  "routes": {
    "main": "Create deal"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Process the inquiry into its commercial opportunity.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Create or reuse the Request’s Deal, copying inquiry context, commercial defaults, selected-product quantity-one Outputs and file references. Ordinary Deal Add is unavailable.",
      "entities": [
        {
          "entity": "deal",
          "effect": "creates",
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
            "Owner",
            "Co-owner",
            "Department",
            "Request",
            "Company",
            "Contact person",
            "Lead",
            "Partner contact",
            "Ticket",
            "Tags",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "output",
          "effect": "creates",
          "with": "deal",
          "facts": [
            "Product",
            "Quantity",
            "Amount",
            "Currency",
            "Planned shipment date",
            "Contract shipment date",
            "Actual shipment date",
            "Serial information",
            "Shipped",
            "Deal",
            "Created",
            "Updated",
            "Modified by"
          ]
        },
        {
          "entity": "file",
          "effect": "creates",
          "with": "deal",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ]
        },
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Pending",
            "Deal"
          ]
        },
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Deal"
          ]
        },
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    }
  ]
}
---

# Create deal

## Trigger

Operator invokes Create deal.

## Outcome

Create or reuse the Request’s Deal, copying inquiry context, commercial defaults, selected-product quantity-one Outputs and file references. Ordinary Deal Add is unavailable.

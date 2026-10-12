---
{
  "entities": [
    {
      "entity": "deal",
      "shows": [
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
      ],
      "collects": [
        "Name",
        "Description",
        "Translation",
        "Amount",
        "Currency",
        "Tier name",
        "Discount type",
        "Discount",
        "Stage",
        "Active",
        "Relevant",
        "Important",
        "New",
        "Closing reason",
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
        "Tags"
      ]
    },
    {
      "entity": "deal-stage",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "closing-reason",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "client-type",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "currency",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "department",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "company",
      "shows": [
        "Full name"
      ]
    },
    {
      "entity": "contact-person",
      "shows": [
        "First name",
        "Last name"
      ]
    },
    {
      "entity": "lead",
      "shows": [
        "First name",
        "Last name"
      ]
    },
    {
      "entity": "output",
      "shows": [
        "Product",
        "Quantity"
      ]
    },
    {
      "entity": "payment",
      "shows": [
        "Amount",
        "Currency"
      ]
    },
    {
      "entity": "activity-log",
      "shows": [
        "Entries"
      ]
    },
    {
      "entity": "transaction-quality-event",
      "shows": [
        "Deal",
        "Signal"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Filename",
        "Media location"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    }
  ]
}
---

# Deal record

Commercial facts, counterparties, stage, activity/relevance, closing facts, follow-up, Outputs, Payments, quality and workflow.

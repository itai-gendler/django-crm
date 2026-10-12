---
{
  "entities": [
    {
      "entity": "request",
      "shows": [
        "Subject",
        "Description",
        "Remark",
        "Translation",
        "Person name",
        "Email address",
        "Telephone",
        "Company name",
        "Receipt date",
        "Attribution",
        "Source",
        "Ticket",
        "Country",
        "City",
        "Owner",
        "Co-owner",
        "Department",
        "Pending",
        "Duplicate",
        "Case",
        "Subsequent",
        "Verification required",
        "Products",
        "Company",
        "Contact person",
        "Lead",
        "Deal",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Subject",
        "Description",
        "Remark",
        "Translation",
        "Person name",
        "Email address",
        "Telephone",
        "Company name",
        "Receipt date",
        "Attribution",
        "Source",
        "Country",
        "City",
        "Owner",
        "Co-owner",
        "Department",
        "Duplicate",
        "Case",
        "Verification required",
        "Products",
        "Company",
        "Contact person",
        "Lead",
        "Deal"
      ]
    },
    {
      "entity": "lead-source",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "country",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "city",
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
      "entity": "product",
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
      "target": "crm/models/request.py"
    }
  ]
}
---

# Request record

Inquiry, source/ticket, contact and location details, counterparties, selected Products, responsibility, pending/duplicate/case flags.

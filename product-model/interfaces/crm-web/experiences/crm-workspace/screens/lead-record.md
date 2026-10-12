---
{
  "entities": [
    {
      "entity": "lead",
      "shows": [
        "First name",
        "Last name",
        "Title",
        "Avatar",
        "Company name",
        "Description",
        "Qualification",
        "Telephone",
        "Other telephone",
        "Mobile",
        "Email address",
        "Website",
        "Address",
        "Country",
        "City",
        "Last contact",
        "Source",
        "Client types",
        "Industries",
        "Tags",
        "Mailing eligibility",
        "Company",
        "Contact person",
        "Owner",
        "Department",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "First name",
        "Last name",
        "Title",
        "Avatar",
        "Company name",
        "Description",
        "Qualification",
        "Telephone",
        "Other telephone",
        "Mobile",
        "Email address",
        "Website",
        "Address",
        "Country",
        "City",
        "Last contact",
        "Source",
        "Client types",
        "Industries",
        "Tags",
        "Mailing eligibility",
        "Company",
        "Contact person",
        "Owner",
        "Department"
      ]
    },
    {
      "entity": "industry",
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
      "entity": "client-type",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "crm-tag",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "lead-source",
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
      "target": "crm/models/lead.py"
    }
  ]
}
---

# Lead record

Provisional person/company facts, qualification, industries, conversion links, avatar, responsibility and mailing eligibility.

---
{
  "entities": [
    {
      "entity": "company",
      "shows": [
        "Full name",
        "Alternative names",
        "Registration number",
        "Logo",
        "Description",
        "Qualification",
        "Telephone",
        "Other telephone",
        "Email address",
        "Website",
        "Address",
        "Country",
        "City",
        "Client types",
        "Industries",
        "Tags",
        "Mailing eligibility",
        "Owner",
        "Department",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Full name",
        "Alternative names",
        "Registration number",
        "Logo",
        "Description",
        "Qualification",
        "Telephone",
        "Other telephone",
        "Email address",
        "Website",
        "Address",
        "Country",
        "City",
        "Client types",
        "Industries",
        "Tags",
        "Mailing eligibility",
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
      "target": "crm/models/company.py"
    }
  ]
}
---

# Company record

Corporate identity, qualification, contact/address details, industries, tags, owner/department and mailing eligibility.

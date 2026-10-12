---
{
  "entities": [
    {
      "entity": "contact-person",
      "shows": [
        "First name",
        "Last name",
        "Title",
        "Birth date",
        "Sex",
        "Avatar",
        "Description",
        "Telephone",
        "Other telephone",
        "Mobile",
        "Email address",
        "Address",
        "Country",
        "City",
        "Last contact",
        "Source",
        "Mailing eligibility",
        "Company",
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
        "Birth date",
        "Sex",
        "Avatar",
        "Description",
        "Telephone",
        "Other telephone",
        "Mobile",
        "Email address",
        "Address",
        "Country",
        "City",
        "Last contact",
        "Source",
        "Mailing eligibility",
        "Company",
        "Owner",
        "Department"
      ]
    },
    {
      "entity": "company",
      "shows": [
        "Full name"
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
      "target": "crm/models/contact.py"
    }
  ]
}
---

# Contact person record

Person/contact information, Company, source, avatar, owner/department and mailing eligibility.

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
      ]
    },
    {
      "entity": "contact-person",
      "shows": [
        "First name",
        "Last name",
        "Email address"
      ]
    },
    {
      "entity": "lead",
      "shows": [
        "First name",
        "Last name",
        "Company name",
        "Email address"
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

# Duplicate consolidation

Original/duplicate selection and processing result.

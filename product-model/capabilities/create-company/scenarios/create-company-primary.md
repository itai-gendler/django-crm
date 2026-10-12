---
{
  "kind": "primary",
  "routes": {
    "main": "Create company"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save corporate identity, qualification and contact details.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Company is retained with Full name, Alternative names, Registration number, Logo, Description. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "company",
          "effect": "creates",
          "facts": [
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
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
    }
  ]
}
---

# Create company

## Trigger

Operator invokes Create company.

## Outcome

A distinct Company is retained with Full name, Alternative names, Registration number, Logo, Description. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

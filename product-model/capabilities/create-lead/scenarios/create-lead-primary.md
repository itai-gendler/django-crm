---
{
  "kind": "primary",
  "routes": {
    "main": "Create lead"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save provisional person and corporate contact information.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Lead is retained with First name, Last name, Title, Avatar, Company name. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
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
          ]
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    }
  ]
}
---

# Create lead

## Trigger

Operator invokes Create lead.

## Outcome

A distinct Lead is retained with First name, Last name, Title, Avatar, Company name. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

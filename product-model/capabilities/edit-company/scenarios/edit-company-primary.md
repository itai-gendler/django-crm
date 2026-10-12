---
{
  "kind": "primary",
  "routes": {
    "main": "Edit company"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Company and invoke edit.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected Company retains the submitted Full name, Alternative names, Registration number, Logo, Description, Qualification, Telephone, Other telephone. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "company",
          "effect": "changes",
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
            "Mailing eligibility",
            "Department"
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

# Edit company

## Trigger

Operator invokes Edit company.

## Outcome

The selected Company retains the submitted Full name, Alternative names, Registration number, Logo, Description, Qualification, Telephone, Other telephone. Read-only fields retain their previous values and invalid form input returns field errors.

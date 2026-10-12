---
{
  "kind": "primary",
  "routes": {
    "main": "Edit lead"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Lead and invoke edit.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected Lead retains the submitted First name, Last name, Title, Company name, Description, Qualification, Telephone, Other telephone. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "First name",
            "Last name",
            "Title",
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
            "Mailing eligibility",
            "Company",
            "Contact person",
            "Department"
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

# Edit lead

## Trigger

Operator invokes Edit lead.

## Outcome

The selected Lead retains the submitted First name, Last name, Title, Company name, Description, Qualification, Telephone, Other telephone. Read-only fields retain their previous values and invalid form input returns field errors.

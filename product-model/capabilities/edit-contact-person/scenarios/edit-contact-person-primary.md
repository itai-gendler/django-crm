---
{
  "kind": "primary",
  "routes": {
    "main": "Edit contact person"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Contact person and invoke edit.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected Contact person retains the submitted First name, Last name, Title, Birth date, Sex, Description, Telephone, Other telephone. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "changes",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Birth date",
            "Sex",
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
            "Department"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/contactadmin.py"
    }
  ]
}
---

# Edit contact person

## Trigger

Operator invokes Edit contact person.

## Outcome

The selected Contact person retains the submitted First name, Last name, Title, Birth date, Sex, Description, Telephone, Other telephone. Read-only fields retain their previous values and invalid form input returns field errors.

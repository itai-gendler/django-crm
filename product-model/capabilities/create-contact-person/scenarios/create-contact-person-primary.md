---
{
  "kind": "primary",
  "routes": {
    "main": "Create contact person"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Save the person’s name, contact details and corporate association.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Contact person is retained with First name, Last name, Title, Birth date, Sex. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "creates",
          "facts": [
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

# Create contact person

## Trigger

Operator invokes Create contact person.

## Outcome

A distinct Contact person is retained with First name, Last name, Title, Birth date, Sex. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

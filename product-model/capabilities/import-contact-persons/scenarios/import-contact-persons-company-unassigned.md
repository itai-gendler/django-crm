---
{
  "kind": "edge",
  "routes": {
    "main": "Import contact persons — company unassigned"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The imported Contact person has no uniquely matched Company.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the workbook or remote-message selection for processing.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::counterparty-import"
        }
      }
    },
    {
      "kind": "product",
      "text": "The imported Contact person remains without an invented matching Company.",
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
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::counterparty-import"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmadminsite.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/create_objects.py"
    }
  ]
}
---

# Import contact persons — company unassigned

## Trigger

Operator invokes Import contact persons.

## Outcome

The imported Contact person remains without an invented matching Company.

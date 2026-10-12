---
{
  "kind": "edge",
  "routes": {
    "main": "Import leads — row error reported"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "At least one valid earlier import row is saved before another row fails processing.",
      "entities": []
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
      "text": "The row error is retained through the notices/report path; other rows may already have been saved.",
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

# Import leads — row error reported

## Trigger

Operator invokes Import leads.

## Outcome

The row error is retained through the notices/report path; other rows may already have been saved.

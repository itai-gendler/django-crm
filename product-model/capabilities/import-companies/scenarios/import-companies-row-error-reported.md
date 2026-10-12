---
{
  "kind": "edge",
  "routes": {
    "main": "Import companies — row error reported"
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

# Import companies — row error reported

## Trigger

Operator invokes Import companies.

## Outcome

The row error is retained through the notices/report path; other rows may already have been saved.

---
{
  "kind": "primary",
  "routes": {
    "main": "Import companies"
  },
  "steps": [
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
      "actor": "operator",
      "text": "The workbook upload starts background processing and opens the corresponding browser with a queued-processing notice; that response does not establish row completion.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::counterparty-import"
        }
      }
    },
    {
      "kind": "product",
      "text": "After accepting the workbook, the background processor saves its valid nonduplicate row with the imported contact information and source defaults.",
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

# Import companies

## Trigger

Operator invokes Import companies.

## Outcome

The upload is queued and the corresponding browser opens. On the successful row-processing path, its valid nonduplicate row is subsequently retained.

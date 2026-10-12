---
{
  "kind": "primary",
  "routes": {
    "main": "Import contact persons"
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

# Import contact persons

## Trigger

Operator invokes Import contact persons.

## Outcome

The upload is queued and the corresponding browser opens. On the successful row-processing path, its valid nonduplicate row is subsequently retained.

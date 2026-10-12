---
{
  "kind": "edge",
  "routes": {
    "main": "Import companies — duplicate skipped"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The import candidate matches the subject-specific duplicate key of an existing saved record.",
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
      "text": "The existing duplicate-key record is retained and another imported record is not added.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [
            "Full name",
            "Alternative names",
            "Registration number",
            "Logo"
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

# Import companies — duplicate skipped

## Trigger

Operator invokes Import companies.

## Outcome

The existing duplicate-key record is retained and another imported record is not added.

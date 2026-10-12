---
{
  "kind": "edge",
  "routes": {
    "main": "Import contact persons — duplicate skipped"
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
          "entity": "contact-person",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Birth date"
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

# Import contact persons — duplicate skipped

## Trigger

Operator invokes Import contact persons.

## Outcome

The existing duplicate-key record is retained and another imported record is not added.

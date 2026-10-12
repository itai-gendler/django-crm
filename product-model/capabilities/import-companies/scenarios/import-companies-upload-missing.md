---
{
  "kind": "validation",
  "routes": {
    "main": "Import companies — upload missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The import request supplies no workbook upload.",
      "entities": [
        {
          "entity": "request",
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
      "text": "Missing upload is rejected without starting the processing thread.",
      "entities": [],
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

# Import companies — upload missing

## Trigger

Operator invokes Import companies.

## Outcome

Missing upload is rejected without starting the processing thread.

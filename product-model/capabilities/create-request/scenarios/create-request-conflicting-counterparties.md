---
{
  "kind": "validation",
  "routes": {
    "main": "Create request — conflicting counterparties"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted inquiry names incompatible counterparty relationships.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the inquiry details and attribution.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Conflicting counterparty input is rejected without saving that invalid record.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/forms/admin_forms.py"
    }
  ]
}
---

# Create request — conflicting counterparties

## Trigger

Operator invokes Create request.

## Outcome

Conflicting counterparty input is rejected without saving that invalid record.

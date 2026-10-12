---
{
  "kind": "validation",
  "routes": {
    "main": "Print request — outside queryset or view grant"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected record cannot be resolved through the printing handler’s queryset or view check.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Attempt to open the selected subject URL.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Printing is refused for the unavailable selected record.",
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

# Print request — outside queryset or view grant

## Trigger

Operator invokes Print request.

## Outcome

Printing is refused for the unavailable selected record.

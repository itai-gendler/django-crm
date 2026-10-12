---
{
  "kind": "validation",
  "routes": {
    "main": "Print Email — outside queryset or view grant"
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
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Printing is refused for the unavailable selected record.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Print Email — outside queryset or view grant

## Trigger

Operator invokes Print Email.

## Outcome

Printing is refused for the unavailable selected record.

---
{
  "kind": "primary",
  "routes": {
    "main": "Delete request"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Request and invoke delete.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Remove the selected Request.",
      "entities": [
        {
          "entity": "request",
          "effect": "removes"
        }
      ],
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

# Delete request

## Trigger

Operator invokes Delete request.

## Outcome

Remove the selected Request.

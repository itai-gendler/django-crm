---
{
  "kind": "primary",
  "routes": {
    "main": "Activate case"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Invoke the offered activate control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Product saves: existing case Request is reactivated by setting Pending; its Case classification is preserved.",
      "entities": [
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Pending"
          ]
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

# Activate case

## Trigger

Operator invokes Activate case.

## Outcome

The existing case Request is reactivated by setting Pending; its Case classification is preserved.

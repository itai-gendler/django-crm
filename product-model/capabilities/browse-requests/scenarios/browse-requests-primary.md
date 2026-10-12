---
{
  "kind": "primary",
  "routes": {
    "main": "Browse requests"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Request and invoke browse.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "Present the source-defined Request selection, search/filter results and summary facts.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": [
            "Subject",
            "Description",
            "Remark",
            "Translation",
            "Person name",
            "Email address",
            "Telephone",
            "Company name"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-browser"
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

# Browse requests

## Trigger

Operator invokes Browse requests.

## Outcome

Present the source-defined Request selection, search/filter results and summary facts.

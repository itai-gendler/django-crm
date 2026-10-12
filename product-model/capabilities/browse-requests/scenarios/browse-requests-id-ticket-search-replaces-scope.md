---
{
  "kind": "primary",
  "routes": {
    "main": "Browse requests — id ticket search replaces scope"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The inquiry search uses the ID or ticket special branch.",
      "entities": []
    },
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
      "text": "The ID/ticket search uses the replacement queryset rather than preserving the earlier owner/department scope.",
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
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
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

# Browse requests — id ticket search replaces scope

## Trigger

Operator invokes Browse requests.

## Outcome

The ID/ticket search uses the replacement queryset rather than preserving the earlier owner/department scope.

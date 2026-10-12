---
{
  "kind": "validation",
  "routes": {
    "main": "Edit deal — commercial fields read only"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The current editor has the Chief role whose listed commercial inputs are readonly.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "company-executive",
      "text": "Select Deal and invoke edit.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The read-only commercial fields remain unchanged.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Translation",
            "Amount"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      },
      "actor": "company-executive"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/clarify_permission.py"
    }
  ]
}
---

# Edit deal — commercial fields read only

## Trigger

Company executive submits the stated case.

## Outcome

The read-only commercial fields remain unchanged.

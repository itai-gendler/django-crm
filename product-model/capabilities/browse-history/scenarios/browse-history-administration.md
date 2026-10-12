---
{
  "kind": "primary",
  "routes": {
    "main": "Browse history — administration"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Global audit presentation is requested from restricted administration.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "Select History and invoke browse.",
      "entities": [
        {
          "entity": "history",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::restricted-administration::global-history"
        }
      }
    },
    {
      "kind": "product",
      "text": "The restricted global audit entries are presented.",
      "entities": [
        {
          "entity": "history",
          "effect": "reads",
          "facts": [
            "Actor",
            "Subject representation",
            "Action",
            "Change description",
            "Time"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::restricted-administration::global-history"
        }
      },
      "actor": "crm-administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/basemodeladmin.py"
    }
  ]
}
---

# Browse history — administration

## Trigger

CRM administrator invokes Browse history.

## Outcome

The restricted global audit entries are presented.

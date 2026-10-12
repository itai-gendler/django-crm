---
{
  "kind": "primary",
  "routes": {
    "main": "Browse history"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
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
          "place": "crm-web::crm-workspace::record-history"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected subject’s recorded actions, audit actor and times are presented.",
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
          "place": "crm-web::crm-workspace::record-history"
        }
      },
      "actor": "operator"
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

# Browse history

## Trigger

Operator invokes Browse history.

## Outcome

The selected subject’s recorded actions, audit actor and times are presented.

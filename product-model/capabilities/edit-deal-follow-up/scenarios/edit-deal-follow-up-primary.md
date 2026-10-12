---
{
  "kind": "primary",
  "routes": {
    "main": "Edit deal follow up"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
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
      "text": "The selected Deal retains the submitted Next step, Next step date, Reminder. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "deal",
          "effect": "changes",
          "facts": [
            "Next step",
            "Next step date",
            "Reminder"
          ]
        },
        {
          "entity": "reminder",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      },
      "actor": "operator"
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

# Edit deal follow up

## Trigger

Operator invokes Edit deal follow up.

## Outcome

The selected Deal retains the submitted Next step, Next step date, Reminder. Read-only fields retain their previous values and invalid form input returns field errors.

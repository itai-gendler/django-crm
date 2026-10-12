---
{
  "kind": "primary",
  "routes": {
    "main": "Edit account status"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "Select User and invoke edit.",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected User retains the submitted Active. Read-only fields retain their previous values and invalid form input returns field errors.",
      "entities": [
        {
          "entity": "user",
          "effect": "changes",
          "facts": [
            "Active"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::user-profile-record"
        }
      },
      "actor": "crm-administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ]
}
---

# Edit account status

## Trigger

CRM administrator invokes Edit account status.

## Outcome

The selected User retains the submitted Active. Read-only fields retain their previous values and invalid form input returns field errors.

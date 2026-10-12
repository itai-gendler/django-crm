---
{
  "kind": "primary",
  "routes": {
    "main": "Transfer company ownership — direct staff helper"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected Companies are submitted directly to the staff-wrapped ownership-transfer helper.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "Submit the selected corporate records and replacement owner.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      }
    },
    {
      "kind": "product",
      "text": "The direct staff helper changes selected Company/Contact ownership without the normal action’s exclusive administrator exposure.",
      "entities": [
        {
          "entity": "company",
          "effect": "changes",
          "facts": [
            "Owner",
            "Department"
          ]
        },
        {
          "entity": "contact-person",
          "effect": "changes",
          "facts": [
            "Owner",
            "Department"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      },
      "actor": "crm-administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/change_owner_companies.py"
    }
  ]
}
---

# Transfer company ownership — direct staff helper

## Trigger

CRM administrator invokes Transfer company ownership.

## Outcome

The direct staff helper changes selected Company/Contact ownership without the normal action’s exclusive administrator exposure.

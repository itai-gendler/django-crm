---
{
  "kind": "primary",
  "routes": {
    "main": "Transfer company ownership"
  },
  "steps": [
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
      "text": "Selected Companies and corresponding Contacts receive the selected owner and that owner’s department.",
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
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
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

# Transfer company ownership

## Trigger

CRM administrator invokes Transfer company ownership.

## Outcome

Selected Companies and corresponding Contacts receive the selected owner and that owner’s department.

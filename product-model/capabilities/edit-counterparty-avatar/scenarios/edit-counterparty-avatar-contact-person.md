---
{
  "kind": "primary",
  "routes": {
    "main": "Edit counterparty avatar — contact person"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparty is a Contact person.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Contact person and invoke edit.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Save Lead information exposed by the selected record, preserving separately governed fields. This way uses Contact person.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "changes",
          "facts": [
            "Avatar"
          ]
        },
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/lead.py"
    }
  ]
}
---

# Edit counterparty avatar — contact person

## Trigger

Operator invokes Edit counterparty avatar.

## Outcome

Save Lead information exposed by the selected record, preserving separately governed fields. This way uses Contact person.

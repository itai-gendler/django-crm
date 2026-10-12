---
{
  "kind": "primary",
  "routes": {
    "main": "Delete contact person"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Contact person and invoke delete.",
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
      "text": "Remove the selected Contact person.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "removes"
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
      "target": "crm/site/contactadmin.py"
    }
  ]
}
---

# Delete contact person

## Trigger

Operator invokes Delete contact person.

## Outcome

Remove the selected Contact person.

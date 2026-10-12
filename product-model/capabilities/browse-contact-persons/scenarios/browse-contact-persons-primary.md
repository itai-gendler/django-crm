---
{
  "kind": "primary",
  "routes": {
    "main": "Browse contact persons"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Contact person and invoke browse.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Email address",
            "Telephone",
            "Company",
            "Mailing eligibility",
            "Created",
            "Owner"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
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

# Browse contact persons

## Trigger

Operator invokes Browse contact persons.

## Outcome

Present the source-defined Contact person selection, search/filter results and summary facts.

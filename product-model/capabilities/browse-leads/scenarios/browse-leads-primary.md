---
{
  "kind": "primary",
  "routes": {
    "main": "Browse leads"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Lead and invoke browse.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Email address",
            "Company name",
            "Owner",
            "Mailing eligibility",
            "Created"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-browser"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    }
  ]
}
---

# Browse leads

## Trigger

Operator invokes Browse leads.

## Outcome

Present the source-defined Lead selection, search/filter results and summary facts.

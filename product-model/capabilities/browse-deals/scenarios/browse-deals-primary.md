---
{
  "kind": "primary",
  "routes": {
    "main": "Browse deals"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Deal and invoke browse.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-browser"
        }
      }
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "deal",
          "effect": "reads",
          "facts": [
            "Name",
            "Important",
            "Active",
            "Relevant",
            "Next step",
            "Next step date",
            "Stage",
            "Company",
            "Contact person",
            "Lead"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-browser"
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

# Browse deals

## Trigger

Operator invokes Browse deals.

## Outcome

Present the source-defined Deal selection, search/filter results and summary facts.

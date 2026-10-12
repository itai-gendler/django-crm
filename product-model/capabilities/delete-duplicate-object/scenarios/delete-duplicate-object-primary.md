---
{
  "kind": "primary",
  "routes": {
    "main": "Delete duplicate object"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Company and invoke delete.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [],
          "as": "duplicate"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      }
    },
    {
      "kind": "product",
      "text": "The Product consolidates the original counterparty, rewires its references, removes the duplicate and opens the corresponding browser.",
      "entities": [
        {
          "entity": "company",
          "effect": "changes",
          "facts": [],
          "as": "original"
        },
        {
          "entity": "company",
          "effect": "removes",
          "as": "duplicate"
        },
        {
          "entity": "file",
          "effect": "changes",
          "facts": [
            "Attached subject"
          ]
        },
        {
          "entity": "mailing-out",
          "effect": "changes",
          "facts": [
            "Pending recipients"
          ]
        },
        {
          "entity": "deal",
          "effect": "changes",
          "facts": [
            "Company"
          ]
        },
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Company"
          ]
        },
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Company"
          ]
        },
        {
          "entity": "contact-person",
          "effect": "changes",
          "facts": [
            "Company"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/delete_duplicate_object.py"
    }
  ]
}
---

# Delete duplicate object

## Trigger

Operator invokes Delete duplicate object.

## Outcome

The selected original receives missing counterparty information and combined classification memberships. Related records, pending campaign recipient references and attachment references move from the duplicate to the original. The duplicate and its mailing registration are removed, a success notice is shown, and the corresponding browser opens.

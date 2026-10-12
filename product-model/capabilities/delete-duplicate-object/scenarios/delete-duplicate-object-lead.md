---
{
  "kind": "primary",
  "routes": {
    "main": "Delete duplicate object — lead"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparty is a Lead.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [],
          "as": "duplicate"
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Lead and invoke delete.",
      "entities": [
        {
          "entity": "lead",
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
          "entity": "lead",
          "effect": "changes",
          "facts": [],
          "as": "original"
        },
        {
          "entity": "lead",
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
            "Lead"
          ]
        },
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Lead"
          ]
        },
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Lead"
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

# Delete duplicate object — lead

## Trigger

Operator invokes Delete duplicate object.

## Outcome

The selected original receives missing counterparty information and combined classification memberships. Related records, pending campaign recipient references and attachment references move from the duplicate to the original. The duplicate and its mailing registration are removed, a success notice is shown, and the corresponding browser opens.

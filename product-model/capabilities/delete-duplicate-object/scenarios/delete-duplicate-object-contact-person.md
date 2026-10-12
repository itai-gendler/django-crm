---
{
  "kind": "primary",
  "routes": {
    "main": "Delete duplicate object — contact person"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected counterparty is a Contact person.",
      "entities": [
        {
          "entity": "contact-person",
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
      "text": "Select Contact person and invoke delete.",
      "entities": [
        {
          "entity": "contact-person",
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
          "entity": "contact-person",
          "effect": "changes",
          "facts": [],
          "as": "original"
        },
        {
          "entity": "contact-person",
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
            "Contact person"
          ]
        },
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Contact person"
          ]
        },
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Contact person"
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

# Delete duplicate object — contact person

## Trigger

Operator invokes Delete duplicate object.

## Outcome

The selected original receives missing counterparty information and combined classification memberships. Related records, pending campaign recipient references and attachment references move from the duplicate to the original. The duplicate and its mailing registration are removed, a success notice is shown, and the corresponding browser opens.

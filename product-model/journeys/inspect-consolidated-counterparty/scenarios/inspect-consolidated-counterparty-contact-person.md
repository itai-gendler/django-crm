---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      "actor": "operator",
      "capability": "delete-duplicate-object"
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
      },
      "capability": "delete-duplicate-object"
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
      "actor": "operator",
      "capability": "delete-duplicate-object"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "delete-duplicate-object",
      "text": "The Product opens the counterparty-person browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Contact person and invoke browse.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": [],
          "as": "original"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
        }
      },
      "capability": "browse-contact-persons"
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
          ],
          "as": "original"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::contact-person-browser"
        }
      },
      "actor": "operator",
      "capability": "browse-contact-persons"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/delete_duplicate_object.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
    }
  ]
}
---

# Inspect consolidated counterparty — contact person

## Trigger

The operator starts by select Contact person and invoke delete.

## Outcome

The operator consolidates a Company, Contact person or Lead duplicate, then reaches the corresponding browser with the original counterparty and rewired references retained and the duplicate removed.

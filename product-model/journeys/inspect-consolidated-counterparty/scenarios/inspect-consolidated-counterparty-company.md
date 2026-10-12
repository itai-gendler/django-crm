---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
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
      },
      "capability": "delete-duplicate-object"
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
      "actor": "operator",
      "capability": "delete-duplicate-object"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "delete-duplicate-object",
      "text": "The Product opens the companies browser for the next action.",
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
      "text": "Select Company and invoke browse.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [],
          "as": "original"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      },
      "capability": "browse-companies"
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [
            "Full name",
            "Client types",
            "Created",
            "Owner",
            "Mailing eligibility",
            "Registration number"
          ],
          "as": "original"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      },
      "actor": "operator",
      "capability": "browse-companies"
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

# Inspect consolidated counterparty — company

## Trigger

The operator starts by select Company and invoke delete.

## Outcome

The operator consolidates a Company, Contact person or Lead duplicate, then reaches the corresponding browser with the original counterparty and rewired references retained and the duplicate removed.

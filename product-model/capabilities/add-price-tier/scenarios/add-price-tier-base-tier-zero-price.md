---
{
  "kind": "primary",
  "routes": {
    "main": "Add price tier — base tier zero price"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "A base rule exists but its Product has no corresponding base tier yet.",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "sales-manager"
    },
    {
      "kind": "actor",
      "actor": "sales-manager",
      "text": "Save the existing Product using its price-tier generation control.",
      "entities": [
        {
          "entity": "product",
          "effect": "reads",
          "facts": [
            "Name",
            "Category",
            "Department"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      }
    },
    {
      "kind": "product",
      "actor": "sales-manager",
      "text": "Save Product first, retaining Modified by and update time; supply the selected department only if Product has no department. Then dispatch tier generation.",
      "entities": [
        {
          "entity": "product",
          "effect": "changes",
          "facts": [
            "Modified by",
            "Updated",
            "Department"
          ]
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The first base tier is retained at zero with its pricing warning.",
      "entities": [
        {
          "entity": "product-price-tier",
          "effect": "creates",
          "facts": [
            "Tier name",
            "Price",
            "Minimum quantity",
            "Valid from",
            "Valid to",
            "Description",
            "Product",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::product-record"
        }
      },
      "actor": "sales-manager"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/productadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/tieredpricinginline.py"
    }
  ]
}
---

# Add price tier — base tier zero price

## Trigger

Sales manager saves the existing Product with price-tier generation selected.

## Outcome

The first base tier is retained at zero with its pricing warning.

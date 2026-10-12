---
{
  "kind": "primary",
  "routes": {
    "main": "Add price tier"
  },
  "steps": [
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
      "text": "Missing tiers are generated from category rules when present, otherwise department rules. Existing names are skipped and nonbase calculation uses the retained nonzero base price.",
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

# Add price tier

## Trigger

Sales manager saves the existing Product with price-tier generation selected.

## Outcome

Missing tiers are generated from category rules when present, otherwise department rules. Existing names are skipped and nonbase calculation uses the retained nonzero base price.

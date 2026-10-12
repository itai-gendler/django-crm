---
{
  "kind": "validation",
  "routes": {
    "main": "Add price tier — base price zero"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The existing base tier has zero price before further generation.",
      "entities": []
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
      "text": "Further generation is refused until the base price is nonzero.",
      "entities": [
        {
          "entity": "product-price-tier",
          "effect": "reads",
          "facts": [
            "Tier name",
            "Price",
            "Minimum quantity",
            "Valid from"
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

# Add price tier — base price zero

## Trigger

Sales manager saves the existing Product with price-tier generation selected.

## Outcome

Further generation is refused until the base price is nonzero.

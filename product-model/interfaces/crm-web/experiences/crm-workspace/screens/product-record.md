---
{
  "entities": [
    {
      "entity": "product",
      "shows": [
        "Name",
        "Description",
        "Type",
        "Category",
        "Image",
        "Department",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Name",
        "Description",
        "Type",
        "Category",
        "Image"
      ]
    },
    {
      "entity": "product-category",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "client-type",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "department",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "product-price-tier",
      "shows": [
        "Tier name",
        "Price"
      ]
    },
    {
      "entity": "department-price-rule",
      "shows": [
        "Department",
        "Tier name"
      ]
    },
    {
      "entity": "category-price-rule",
      "shows": [
        "Category",
        "Tier name"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Filename",
        "Media location"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/product.py"
    }
  ]
}
---

# Product record

Name, description, goods/service type, category, image, attachments and tiers.

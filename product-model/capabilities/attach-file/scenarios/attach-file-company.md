---
{
  "kind": "primary",
  "routes": {
    "main": "Attach file — company"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The upload or selection uses the selected Company.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the attachment for the selected subject.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The attachment belongs to the selected Company.",
      "entities": [
        {
          "entity": "file",
          "effect": "creates",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ]
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/get_file_links.py"
    }
  ]
}
---

# Attach file — company

## Trigger

Operator invokes Attach file.

## Outcome

The attachment belongs to the selected Company.

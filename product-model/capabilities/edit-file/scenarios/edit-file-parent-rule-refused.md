---
{
  "kind": "validation",
  "routes": {
    "main": "Edit file — parent rule refused"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The selected host or current account fails the corresponding inline/host Rule’s checks.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select File and invoke edit.",
      "entities": [
        {
          "entity": "file",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The attachment/tag mutation is refused.",
      "entities": [
        {
          "entity": "file",
          "effect": "reads",
          "facts": [
            "Filename",
            "Media location",
            "Attached subject",
            "Attached to Deal"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
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

# Edit file — parent rule refused

## Trigger

Operator invokes Edit file.

## Outcome

The attachment/tag mutation is refused.

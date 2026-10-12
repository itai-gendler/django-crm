---
{
  "kind": "primary",
  "routes": {
    "main": "Edit file"
  },
  "steps": [
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
      "text": "The replacement attachment is saved on the same subject; its filename and advertised media location follow the submitted file.",
      "entities": [
        {
          "entity": "file",
          "effect": "changes",
          "facts": [
            "Filename",
            "Media location"
          ]
        },
        {
          "entity": "deal",
          "effect": "reads",
          "facts": []
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

# Edit file

## Trigger

Operator invokes Edit file.

## Outcome

The replacement attachment is saved on the same subject; its filename and advertised media location follow the submitted file.

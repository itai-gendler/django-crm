---
{
  "kind": "edge",
  "routes": {
    "main": "Download file — missing file link"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The attachment has no usable advertised media location.",
      "entities": [
        {
          "entity": "file",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Invoke the offered download control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "No usable media link is produced.",
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

# Download file — missing file link

## Trigger

Operator invokes Download file.

## Outcome

No usable media link is produced.

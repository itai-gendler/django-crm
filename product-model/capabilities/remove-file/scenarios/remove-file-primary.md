---
{
  "kind": "primary",
  "routes": {
    "main": "Remove file"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select File and invoke remove.",
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
      "text": "The selected file membership is removed from the saved File. Other retained memberships are preserved.",
      "entities": [
        {
          "entity": "file",
          "effect": "removes"
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

# Remove file

## Trigger

Operator invokes Remove file.

## Outcome

The selected file membership is removed from the saved File. Other retained memberships are preserved.

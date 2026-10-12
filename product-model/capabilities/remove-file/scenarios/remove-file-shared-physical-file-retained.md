---
{
  "kind": "edge",
  "routes": {
    "main": "Remove file — shared physical file retained"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Another attachment record references the same physical file as the attachment being removed.",
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
      "text": "The attachment is removed while another reference retains its physical storage.",
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

# Remove file — shared physical file retained

## Trigger

Operator invokes Remove file.

## Outcome

The attachment is removed while another reference retains its physical storage.

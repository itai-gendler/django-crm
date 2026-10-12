---
{
  "kind": "primary",
  "routes": {
    "main": "Attach file"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the attachment for the selected subject.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::deal-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The uploaded File reference is retained on the selected subject and its filename and advertised media link are shown with that subject.",
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

# Attach file

## Trigger

Operator invokes Attach file.

## Outcome

The uploaded File reference is retained on the selected subject and its filename and advertised media link are shown with that subject.

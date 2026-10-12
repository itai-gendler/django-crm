---
{
  "kind": "primary",
  "routes": {
    "main": "Download file"
  },
  "steps": [
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
      "text": "The Product presents the retained File media link for the selected subject; the actor follows that advertised location.",
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

# Download file

## Trigger

Operator invokes Download file.

## Outcome

The advertised media location is opened. Byte delivery follows the deployment’s media-serving behavior.

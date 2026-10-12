---
{
  "kind": "primary",
  "routes": {
    "main": "Attach file — quality event"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The upload is attached to the selected Transaction quality event.",
      "entities": [
        {
          "entity": "transaction-quality-event",
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
          "place": "crm-web::crm-workspace::transaction-quality-event-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The attachment belongs to the selected Transaction quality event.",
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
          "entity": "transaction-quality-event",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::transaction-quality-event-record"
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

# Attach file — quality event

## Trigger

Operator invokes Attach file.

## Outcome

The attachment belongs to the selected Transaction quality event.

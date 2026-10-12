---
{
  "kind": "edge",
  "routes": {
    "main": "Submit request — api stop phrase suppression"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The website inquiry text matches a retained Stop phrase.",
      "entities": [
        {
          "entity": "stop-phrase",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "website",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "website"
    },
    {
      "kind": "actor",
      "actor": "website",
      "text": "Submit the commercial inquiry and supplied verification input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "website-requests"
        }
      }
    },
    {
      "kind": "product",
      "text": "API outward success occurs without inquiry persistence and the phrase occurrence is updated.",
      "entities": [
        {
          "entity": "stop-phrase",
          "effect": "changes",
          "facts": [
            "Last occurrence"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "website-requests"
        }
      },
      "actor": "website"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/add_request.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/contact_form.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/create_form_request.py"
    }
  ]
}
---

# Submit request — api stop phrase suppression

## Trigger

Website invokes Submit request.

## Outcome

API outward success occurs without inquiry persistence and the phrase occurrence is updated.

---
{
  "kind": "validation",
  "routes": {
    "main": "Submit request — api source unknown"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The supplied website source token has no matching configured source.",
      "entities": [
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
      "text": "Unknown API source returns 401 without inquiry creation.",
      "entities": [],
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

# Submit request — api source unknown

## Trigger

Website invokes Submit request.

## Outcome

Unknown API source returns 401 without inquiry creation.

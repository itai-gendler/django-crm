---
{
  "kind": "validation",
  "routes": {
    "main": "Submit request — api captcha rejected"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The website request supplies a CAPTCHA token whose validation fails.",
      "entities": [
        {
          "entity": "website",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "request",
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
      "text": "The supplied API CAPTCHA is rejected without inquiry creation.",
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

# Submit request — api captcha rejected

## Trigger

Website invokes Submit request.

## Outcome

The supplied API CAPTCHA is rejected without inquiry creation.

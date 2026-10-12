---
{
  "kind": "validation",
  "routes": {
    "main": "Submit request — api nonpost"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The website inquiry endpoint receives a method other than POST.",
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
      "text": "The method-refusal response creates no inquiry.",
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

# Submit request — api nonpost

## Trigger

Website invokes Submit request.

## Outcome

The method-refusal response creates no inquiry.

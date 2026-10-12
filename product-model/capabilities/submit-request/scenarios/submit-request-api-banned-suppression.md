---
{
  "kind": "edge",
  "routes": {
    "main": "Submit request — api banned suppression"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The website POST includes a banned corporate name, reaching suppression before source resolution.",
      "entities": [
        {
          "entity": "website",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "resolution",
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
      "text": "API outward success occurs without persisting the banned inquiry; this suppression can precede source lookup.",
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

# Submit request — api banned suppression

## Trigger

Website invokes Submit request.

## Outcome

API outward success occurs without persisting the banned inquiry; this suppression can precede source lookup.

---
{
  "kind": "edge",
  "routes": {
    "main": "Submit request — web banned suppression"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The public form includes a banned corporate name.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "inquirer",
      "text": "Submit the commercial inquiry and supplied verification input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::public::contact-form"
        }
      }
    },
    {
      "kind": "product",
      "text": "Web outward success occurs without persisting the banned inquiry.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::public::contact-form"
        }
      },
      "actor": "inquirer"
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

# Submit request — web banned suppression

## Trigger

Inquirer invokes Submit request.

## Outcome

Web outward success occurs without persisting the banned inquiry.

---
{
  "kind": "validation",
  "routes": {
    "main": "Submit request — web invalid"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The submitted public contact form has invalid required values.",
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
      "text": "The form is presented with validation errors and no saved inquiry.",
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

# Submit request — web invalid

## Trigger

Inquirer invokes Submit request.

## Outcome

The form is presented with validation errors and no saved inquiry.

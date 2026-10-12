---
{
  "kind": "validation",
  "routes": {
    "main": "Submit request — web source unknown"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The public form’s source identifier has no configured source.",
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
      "text": "The unresolved web source produces no accepted inquiry.",
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

# Submit request — web source unknown

## Trigger

Inquirer invokes Submit request.

## Outcome

The unresolved web source produces no accepted inquiry.

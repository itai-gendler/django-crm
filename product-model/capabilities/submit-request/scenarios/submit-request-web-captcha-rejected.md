---
{
  "kind": "validation",
  "routes": {
    "main": "Submit request — web captcha rejected"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The public form supplies a CAPTCHA token whose validation fails.",
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
      "text": "The supplied web CAPTCHA is rejected without inquiry creation.",
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

# Submit request — web captcha rejected

## Trigger

Inquirer invokes Submit request.

## Outcome

The supplied web CAPTCHA is rejected without inquiry creation.

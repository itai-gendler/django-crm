---
{
  "kind": "edge",
  "routes": {
    "main": "Submit request — web stop phrase suppression"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The public form’s inquiry text matches a retained Stop phrase.",
      "entities": [
        {
          "entity": "stop-phrase",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "inquirer"
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
      "text": "Web outward success occurs without inquiry persistence and the phrase occurrence is updated.",
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

# Submit request — web stop phrase suppression

## Trigger

Inquirer invokes Submit request.

## Outcome

Web outward success occurs without inquiry persistence and the phrase occurrence is updated.

---
{
  "kind": "primary",
  "routes": {
    "main": "Submit request"
  },
  "steps": [
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
      "text": "The valid public inquiry is retained as a pending Request with its source, contact information and generated ticket; the web response reports receipt.",
      "entities": [
        {
          "entity": "request",
          "effect": "creates",
          "facts": [
            "Subject",
            "Description",
            "Remark",
            "Translation",
            "Person name",
            "Email address",
            "Telephone",
            "Company name",
            "Receipt date",
            "Attribution",
            "Source",
            "Ticket",
            "Country",
            "City",
            "Owner",
            "Co-owner",
            "Department",
            "Pending",
            "Duplicate",
            "Case",
            "Subsequent",
            "Verification required",
            "Products",
            "Company",
            "Contact person",
            "Lead",
            "Deal",
            "Created",
            "Updated",
            "Modified by"
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

# Submit request

## Trigger

Inquirer invokes Submit request.

## Outcome

The valid public inquiry is retained as a pending Request with its source, contact information and generated ticket; the web response reports receipt.

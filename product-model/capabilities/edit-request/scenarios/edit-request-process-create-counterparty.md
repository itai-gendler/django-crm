---
{
  "kind": "primary",
  "routes": {
    "main": "Edit request — process create counterparty"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The Request is processed rather than pending, no existing Contact person or Lead matches, and no Company is linked.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Request and invoke edit.",
      "entities": [
        {
          "entity": "request",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Processing saves a new Lead from the inquiry contact, source and location information, assigns its responsibility from the Request, and links it while marking verification required.",
      "entities": [
        {
          "entity": "request",
          "effect": "changes",
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
            "Deal"
          ]
        },
        {
          "entity": "lead",
          "effect": "creates",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Avatar",
            "Company name",
            "Description",
            "Qualification",
            "Telephone",
            "Other telephone",
            "Mobile",
            "Email address",
            "Website",
            "Address",
            "Country",
            "City",
            "Last contact",
            "Source",
            "Client types",
            "Industries",
            "Tags",
            "Mailing eligibility",
            "Company",
            "Contact person",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/forms/admin_forms.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    }
  ]
}
---

# Edit request — process create counterparty

## Trigger

Operator invokes Edit request.

## Outcome

Processing saves a new Lead from the inquiry contact, source and location information, assigns its responsibility from the Request, and links it while marking verification required.

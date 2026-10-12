---
{
  "kind": "primary",
  "routes": {
    "main": "Edit request"
  },
  "steps": [
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
      "text": "The selected Request retains the submitted Subject, Description, Remark, Translation, Person name, Email address, Telephone, Company name. Read-only fields retain their previous values and invalid form input returns field errors.",
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
          "entity": "company",
          "effect": "reads",
          "facts": []
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
    }
  ]
}
---

# Edit request

## Trigger

Operator invokes Edit request.

## Outcome

The selected Request retains the submitted Subject, Description, Remark, Translation, Person name, Email address, Telephone, Company name. Read-only fields retain their previous values and invalid form input returns field errors.

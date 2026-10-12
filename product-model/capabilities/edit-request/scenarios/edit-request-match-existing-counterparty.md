---
{
  "kind": "primary",
  "routes": {
    "main": "Edit request — match existing counterparty"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Inquiry matching finds the existing counterparty supported by the source’s contact/name checks.",
      "entities": []
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
      "text": "Processing links the matching existing counterparty.",
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

# Edit request — match existing counterparty

## Trigger

Operator invokes Edit request.

## Outcome

Processing links the matching existing counterparty.

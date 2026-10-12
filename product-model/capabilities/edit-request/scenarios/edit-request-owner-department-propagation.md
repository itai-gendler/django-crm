---
{
  "kind": "primary",
  "routes": {
    "main": "Edit request — owner department propagation"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The inquiry’s department changes or its owner changes to a Manager, selecting the source’s related-record propagation.",
      "entities": [
        {
          "entity": "department",
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
      "text": "Responsibility and department propagate at the inspected save points.",
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
          "entity": "department",
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

# Edit request — owner department propagation

## Trigger

Operator invokes Edit request.

## Outcome

Responsibility and department propagate at the inspected save points.

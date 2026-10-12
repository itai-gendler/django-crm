---
{
  "kind": "primary",
  "routes": {
    "main": "Convert lead — existing pair"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Conversion resolves a unique existing Company and Contact person.",
      "entities": [
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Invoke the offered convert control with the stated input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "actor": "operator",
      "text": "The Product saves the edited Lead contact and corporate information before resolving conversion targets.",
      "entities": [
        {
          "entity": "lead",
          "effect": "changes",
          "facts": [
            "First name",
            "Last name",
            "Company name",
            "Email address",
            "Telephone",
            "Country",
            "City",
            "Company",
            "Contact person"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The existing Company and Contact person are reused. Linked Deal, Request and Email in CRM references are changed to those counterparties and the source Lead is removed.",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes"
        },
        {
          "entity": "company",
          "effect": "reads",
          "facts": [
            "Full name"
          ]
        },
        {
          "entity": "contact-person",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name"
          ]
        },
        {
          "entity": "deal",
          "effect": "changes",
          "facts": [
            "Lead",
            "Company",
            "Contact person"
          ]
        },
        {
          "entity": "request",
          "effect": "changes",
          "facts": [
            "Lead",
            "Company",
            "Contact person"
          ]
        },
        {
          "entity": "email",
          "effect": "changes",
          "facts": [
            "Lead",
            "Company",
            "Contact person"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/forms/admin_forms.py"
    }
  ]
}
---

# Convert lead — existing pair

## Trigger

Operator invokes Convert lead.

## Outcome

The existing Company and Contact person are reused. Linked Deal, Request and Email in CRM references are changed to those counterparties and the source Lead is removed.

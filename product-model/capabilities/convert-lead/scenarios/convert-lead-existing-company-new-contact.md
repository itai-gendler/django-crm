---
{
  "kind": "primary",
  "routes": {
    "main": "Convert lead — existing company new contact"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "Conversion resolves a unique existing Company but no matching Contact person.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "contact-person",
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
      "text": "The matching Company is reused and a new Contact person is retained. Linked Deal, Request and Email in CRM references are changed to those counterparties and the source Lead is removed.",
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
          "effect": "creates",
          "facts": [
            "First name",
            "Last name",
            "Title",
            "Birth date",
            "Sex",
            "Avatar",
            "Description",
            "Telephone",
            "Other telephone",
            "Mobile",
            "Email address",
            "Address",
            "Country",
            "City",
            "Last contact",
            "Source",
            "Mailing eligibility",
            "Company",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
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

# Convert lead — existing company new contact

## Trigger

Operator invokes Convert lead.

## Outcome

The matching Company is reused and a new Contact person is retained. Linked Deal, Request and Email in CRM references are changed to those counterparties and the source Lead is removed.

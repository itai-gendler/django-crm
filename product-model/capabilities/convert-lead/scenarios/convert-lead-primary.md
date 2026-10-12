---
{
  "kind": "primary",
  "routes": {
    "main": "Convert lead"
  },
  "steps": [
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
      "text": "A new Company and Contact person are retained with the source contact and ownership information. Linked Deal, Request and Email in CRM references are changed to those counterparties and the source Lead is removed; the conversion success notice is displayed.",
      "entities": [
        {
          "entity": "lead",
          "effect": "removes"
        },
        {
          "entity": "company",
          "effect": "creates",
          "facts": [
            "Full name",
            "Alternative names",
            "Registration number",
            "Logo",
            "Description",
            "Qualification",
            "Telephone",
            "Other telephone",
            "Email address",
            "Website",
            "Address",
            "Country",
            "City",
            "Client types",
            "Industries",
            "Tags",
            "Mailing eligibility",
            "Owner",
            "Department",
            "Created",
            "Updated",
            "Modified by"
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
          ],
          "with": "company"
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

# Convert lead

## Trigger

Operator invokes Convert lead.

## Outcome

A new Company and Contact person are retained with the source contact and ownership information. Linked Deal, Request and Email in CRM references are changed to those counterparties and the source Lead is removed; the conversion success notice is displayed.

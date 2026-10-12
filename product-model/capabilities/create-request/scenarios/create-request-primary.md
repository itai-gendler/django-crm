---
{
  "kind": "primary",
  "routes": {
    "main": "Create request"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Submit the inquiry details and attribution.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::request-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "A distinct Request is retained with Subject, Description, Remark, Translation, Person name. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.",
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

# Create request

## Trigger

Operator invokes Create request.

## Outcome

A distinct Request is retained with Subject, Description, Remark, Translation, Person name. Creation assigns the source-defined account, organizational and date defaults; the saved record is reached through its native save response.

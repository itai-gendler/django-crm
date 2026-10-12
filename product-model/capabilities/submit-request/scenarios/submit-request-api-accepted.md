---
{
  "kind": "primary",
  "routes": {
    "main": "Submit request — api accepted"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "A website POST supplies valid inquiry data and a known source token; no suppression branch applies.",
      "entities": [
        {
          "entity": "website",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "website"
    },
    {
      "kind": "actor",
      "actor": "website",
      "text": "Submit the commercial inquiry and supplied verification input.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "website-requests"
        }
      }
    },
    {
      "kind": "product",
      "text": "The API returns 200 after accepted processing.",
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
          "place": "website-requests"
        }
      },
      "actor": "website"
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

# Submit request — api accepted

## Trigger

Website invokes Submit request.

## Outcome

The API returns 200 after accepted processing.

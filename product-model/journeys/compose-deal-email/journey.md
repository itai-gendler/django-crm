---
{
  "actors": [
    "operator"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/create_email.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Compose deal email

## Goal

Prepare Deal correspondence.

## Success criterion

The operator submits the customer or partner attachment selection, reaches the saved Deal-linked draft, edits its content and submits Send. Normal sending saves Sent and opens the correspondence browser.

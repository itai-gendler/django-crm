---
{
  "actors": [
    "operator"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/reply_email.py"
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

# Forward and send

## Goal

Forward correspondence.

## Success criterion

The operator creates a saved forwarding draft with copied content and attachment references, edits its destination/content and submits Send. Normal sending persists Sent and reaches the correspondence browser.

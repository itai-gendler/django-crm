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

# Reply and send

## Goal

Send reply.

## Success criterion

The operator creates a saved reply from the original correspondence, reaches its edit form, saves the reply content and submits Send. Normal sending persists Sent and reaches the correspondence browser.

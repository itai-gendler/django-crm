---
{
  "actors": [
    "operator"
  ],
  "references": [
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

# Inspect sent email

## Goal

Inspect accepted send.

## Success criterion

The operator submits Send and, after normal processing saves Sent, reaches the correspondence browser and inspects its displayed status.

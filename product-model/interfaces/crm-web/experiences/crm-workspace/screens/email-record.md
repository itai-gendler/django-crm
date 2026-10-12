---
{
  "entities": [
    {
      "entity": "email",
      "shows": [
        "Subject",
        "Content",
        "Sender",
        "To",
        "CC",
        "BCC",
        "Signature",
        "Date",
        "Company",
        "Contact person",
        "Lead",
        "Deal",
        "Request"
      ],
      "collects": [
        "Subject",
        "Content",
        "To",
        "CC",
        "BCC",
        "Signature",
        "Company",
        "Contact person",
        "Lead",
        "Deal",
        "Request"
      ]
    },
    {
      "entity": "signature",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "email-account",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "company",
      "shows": [
        "Full name"
      ]
    },
    {
      "entity": "contact-person",
      "shows": [
        "First name",
        "Last name"
      ]
    },
    {
      "entity": "lead",
      "shows": [
        "First name",
        "Last name"
      ]
    },
    {
      "entity": "deal",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "file",
      "shows": [
        "Filename",
        "Media location"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    }
  ]
}
---

# Email record

Correspondence addresses, subject/content, signature and related counterparties/Deal/Request, plus attached files. Incoming/UID and ownership branches change body/signature exposure. Incoming, Sent and Trash are absent as editable inputs; automatic send status follows the sending operation.

---
{
  "entities": [
    {
      "entity": "mailing-out",
      "shows": [
        "Name",
        "Message",
        "Recipient type",
        "Status",
        "Pending recipients",
        "Successful recipients",
        "Failed recipients",
        "Recipient count",
        "Successful count",
        "Failed count",
        "Daily count",
        "Sending date",
        "Report",
        "Email account",
        "Owner",
        "Department",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Message",
        "Status",
        "Report"
      ]
    },
    {
      "entity": "email-message",
      "shows": [
        "Subject"
      ]
    },
    {
      "entity": "email-account",
      "shows": [
        "Name"
      ]
    },
    {
      "entity": "newsletter-recipient",
      "shows": [
        "Subject"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/mailing_out.py"
    }
  ]
}
---

# Mailing out record

Message/type, status, pending/success/failed recipients, counts, account and delivery report.

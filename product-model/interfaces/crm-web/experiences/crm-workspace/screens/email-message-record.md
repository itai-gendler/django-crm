---
{
  "entities": [
    {
      "entity": "email-message",
      "shows": [
        "Subject",
        "Content",
        "Signature",
        "Owner",
        "Department",
        "Created",
        "Updated",
        "Modified by"
      ],
      "collects": [
        "Subject",
        "Content",
        "Signature",
        "Owner"
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
      "target": "massmail/models/email_message.py"
    }
  ]
}
---

# Email message record

Reusable subject/body, signature, ownership and attachments.

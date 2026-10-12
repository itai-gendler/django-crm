---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/create_email.py"
    }
  ],
  "domain": "emails-in-crm"
}
---

# Create linked email

Prepare correspondence from Company, Contact person, Lead or Deal. A GET without Deal attachments opens an unsaved native Add form; its subsequent save creates correspondence. Selecting Deal attachments and submitting that selection saves a linked draft directly and opens its editor.

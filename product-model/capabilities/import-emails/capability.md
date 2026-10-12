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
      "target": "common/views/select_emails_import.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/import_emails.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/restore_imap_emails.py"
    }
  ],
  "domain": "emails-in-crm"
}
---

# Import Emails

Select remote headers for import or consume configured linked-mail queues, retaining ticket linkage, duplicate and CRM-origin skip branches.

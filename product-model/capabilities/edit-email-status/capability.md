---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    },
    {
      "place": "crm-web::restricted-administration"
    }
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/admin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/admin_redirect_middleware.py"
    }
  ],
  "domain": "emails-in-crm"
}
---

# Edit Email status

Edit Incoming, Sent and Trash in the separate administration Email editor. The CRM Email editor exposes none of these submitted inputs; automatic Sent updates follow the sending operation.

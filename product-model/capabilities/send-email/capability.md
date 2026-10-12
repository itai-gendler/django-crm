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
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ],
  "domain": "emails-in-crm"
}
---

# Send Email

Send the saved correspondence through its owner’s main account; caught failure returns to its editor without setting Sent, accepted send sets Sent and opens the browser.

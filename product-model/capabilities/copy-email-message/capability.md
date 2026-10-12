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
      "target": "massmail/views/copy_message.py"
    }
  ],
  "domain": "email-messages"
}
---

# Copy Email message

A distinct saved reusable message copies content, uses the acting account’s default signature or none, assigns the current owner, and opens in its editor.

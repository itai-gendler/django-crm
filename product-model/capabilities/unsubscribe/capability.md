---
{
  "availability": [
    {
      "place": "crm-web::public"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/unsubscribes.py"
    }
  ]
}
---

# Unsubscribe

Resolve the registration token and disable its and its linked counterparty’s mailing eligibility. Unknown tokens redirect without mutation.

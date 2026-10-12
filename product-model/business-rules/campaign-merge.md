---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/mailing_out.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    }
  ]
}
---

# Campaign merge

Compatible owner/type/message required; pending IDs deduplicated without promising all stored counts equal unique recipients.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "file"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ]
}
---

# File sharing retention

Attachment deletion retains physical storage while another attachment record references it.

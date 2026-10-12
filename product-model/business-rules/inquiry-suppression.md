---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request"
    },
    {
      "type": "entity",
      "id": "stop-phrase"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/request.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "settings/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/requestadmin.py"
    }
  ]
}
---

# Inquiry suppression

Banned-name/phrase matching may report success without Request persistence; phrase hit changes last occurrence.

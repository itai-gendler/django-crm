---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "user",
      "effect": "changes",
      "facts": [
        "Active"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::user-profile-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "permits": [
    {
      "actors": [
        "crm-administrator"
      ]
    }
  ]
}
---

# Account status permissions

Changes User active status from Profile; administrator.

---
{
  "access": "restricted",
  "actors": [
    "crm-administrator"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "webcrm/urls.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/site/crmsite.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/admin_redirect_middleware.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/admin.py"
    }
  ]
}
---

# Restricted administration

Product administration reached through the Superuser-restricted administration route. Mapped operations include global History, direct Email flag edits and administration sign-out; Email flags use this Experience without an additional Screen.

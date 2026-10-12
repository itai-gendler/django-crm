---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmmodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Mailing out filtered creation permissions

Creates from filtered subjects; actual staff/admin-view wrapper and owner filter.

The actual requesting User passes the registered staff/admin-view wrapper. Filtered campaign creation uses the current account’s owner-filtered source records and the implemented selection, rather than an unrelated account’s permissions.

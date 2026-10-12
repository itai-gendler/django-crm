---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email",
      "effect": "reads",
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
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email helper reading permissions

Reads original/source correspondence through specified staff helpers; native queryset and object-view checks not reproduced. Printing excluded.

The actual requesting User passes the active Staff wrapper. Linked/reply/forward and original-message helpers resolve the supplied correspondence, related-record or account identifiers as implemented, without a source-object native View or ownership check. Print operations retain their independent native queryset and View test.

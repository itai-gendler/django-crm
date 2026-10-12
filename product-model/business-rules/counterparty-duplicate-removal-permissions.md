---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "company",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "contact-person",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "lead",
      "effect": "removes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/delete_duplicate_object.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/contactadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/leadadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Counterparty duplicate removal permissions

Removes duplicate; staff helper.

The actual requesting User passes the active Staff helper wrapper. Duplicate removal follows the helper’s original/duplicate selection and input checks, with no independent native model Delete or ownership check.

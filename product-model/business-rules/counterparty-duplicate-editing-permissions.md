---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "company",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "contact-person",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "lead",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "deal",
      "effect": "changes",
      "facts": [
        "Company",
        "Contact person",
        "Lead"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "request",
      "effect": "changes",
      "facts": [
        "Company",
        "Contact person",
        "Lead"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "email",
      "effect": "changes",
      "facts": [
        "Company",
        "Contact person",
        "Lead"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "file",
      "effect": "changes",
      "facts": [
        "Attached subject"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "mailing-out",
      "effect": "changes",
      "facts": [
        "Pending recipients"
      ],
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

# Counterparty duplicate editing permissions

Changes original and supported related facts during consolidation; staff helper.

The actual requesting User passes the active Staff helper wrapper. Original and related-record mutations follow the helper’s original/duplicate selection, with no independent native model Change or ownership checks on each affected record.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "company",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "contact-person",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::duplicate-consolidation"
        }
      ]
    },
    {
      "type": "entity",
      "id": "lead",
      "effect": "reads",
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

# Counterparty helper reading permissions

Reads original/duplicate/selection subjects through specified staff helpers; native queryset and object-view checks not assumed.

The actual requesting User passes the active Staff wrapper. The specified consolidation and selection helpers resolve their supplied counterparty identifiers directly, without reproducing the native queryset or object-model View check.

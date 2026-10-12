---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "company",
      "effect": "changes",
      "facts": [
        "Owner",
        "Department"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      ]
    },
    {
      "type": "entity",
      "id": "contact-person",
      "effect": "changes",
      "facts": [
        "Owner",
        "Department"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/change_owner_companies.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmmodeladmin.py"
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
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Company bulk owner permissions

Changes selected Company/Contact ownership and department; administrator exposes normal action, direct helper only staff-gated.

The normal native bulk action is exposed to Superuser; direct helper requests use the actual requesting User’s active Staff wrapper. The helper processes the submitted Companies and replacement owner without a further native Company/Contact Change or ownership test.

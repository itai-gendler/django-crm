---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "Product-carried run"
  },
  "steps": [
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "Submit the selected corporate records and replacement owner.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      },
      "capability": "transfer-company-ownership"
    },
    {
      "kind": "product",
      "text": "Selected Companies and corresponding Contacts receive the selected owner and that owner’s department.",
      "entities": [
        {
          "entity": "company",
          "effect": "changes",
          "facts": [
            "Owner",
            "Department"
          ]
        },
        {
          "entity": "contact-person",
          "effect": "changes",
          "facts": [
            "Owner",
            "Department"
          ]
        },
        {
          "entity": "department",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      },
      "actor": "crm-administrator",
      "capability": "transfer-company-ownership"
    },
    {
      "kind": "product",
      "actor": "crm-administrator",
      "capability": "transfer-company-ownership",
      "text": "The Product opens the companies browser for the next action.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-ownership-transfer"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "crm-administrator",
      "text": "Select Company and invoke browse.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      },
      "capability": "browse-companies"
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "company",
          "effect": "reads",
          "facts": [
            "Full name",
            "Client types",
            "Created",
            "Owner",
            "Mailing eligibility",
            "Registration number"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::company-browser"
        }
      },
      "actor": "crm-administrator",
      "capability": "browse-companies"
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
      "target": "crm/site/companyadmin.py"
    }
  ]
}
---

# Review transferred companies — selected companies

## Trigger

The crm administrator starts by submit the selected corporate records and replacement owner.

## Outcome

The administrator submits selected Companies and a replacement owner, completes the bulk ownership/department changes and reaches the company browser to inspect those records.

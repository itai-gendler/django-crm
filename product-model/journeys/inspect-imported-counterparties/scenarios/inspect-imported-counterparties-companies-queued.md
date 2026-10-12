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
      "actor": "operator",
      "text": "Submit the workbook or remote-message selection for processing.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::counterparty-import"
        }
      },
      "capability": "import-companies"
    },
    {
      "kind": "product",
      "text": "The workbook upload starts background processing and opens the corresponding browser with a queued-processing notice; no imported-row persistence is asserted at this hand-off.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::counterparty-import"
        }
      },
      "actor": "operator",
      "capability": "import-companies"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "import-companies",
      "text": "The workbook upload starts background processing and opens the corresponding browser with a queued-processing notice; no imported-row persistence is asserted at this hand-off.",
      "entities": [],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::counterparty-import"
        }
      }
    },
    {
      "kind": "actor",
      "actor": "operator",
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
      "actor": "operator",
      "capability": "browse-companies"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmadminsite.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/create_objects.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/companyadmin.py"
    }
  ]
}
---

# Inspect imported counterparties — companies queued

## Trigger

The operator starts by submit the workbook or remote-message selection for processing.

## Outcome

The upload is accepted, its queued-processing notice is presented and the corresponding browser is reached. Processing completion is not promised by this handoff.

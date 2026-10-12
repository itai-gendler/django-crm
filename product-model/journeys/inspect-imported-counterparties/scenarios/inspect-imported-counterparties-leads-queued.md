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
      "capability": "import-leads"
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
      "capability": "import-leads"
    },
    {
      "kind": "product",
      "actor": "operator",
      "capability": "import-leads",
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
      "text": "Select Lead and invoke browse.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-browser"
        }
      },
      "capability": "browse-leads"
    },
    {
      "kind": "product",
      "text": "The selected records and their displayed identity, status, responsibility and date information are presented under the source-defined list filters and search.",
      "entities": [
        {
          "entity": "lead",
          "effect": "reads",
          "facts": [
            "First name",
            "Last name",
            "Email address",
            "Company name",
            "Owner",
            "Mailing eligibility",
            "Created"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::lead-browser"
        }
      },
      "actor": "operator",
      "capability": "browse-leads"
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

# Inspect imported counterparties — leads queued

## Trigger

The operator starts by submit the workbook or remote-message selection for processing.

## Outcome

The upload is accepted, its queued-processing notice is presented and the corresponding browser is reached. Processing completion is not promised by this handoff.

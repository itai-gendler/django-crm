---
{
  "actors": [
    "operator"
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

# Inspect imported counterparties

## Goal

Inspect queued import.

## Success criterion

The operator submits a Company, Contact person or Lead upload, sees its accepted queued-processing response and reaches the corresponding browser. This handoff does not promise that background row processing has completed.

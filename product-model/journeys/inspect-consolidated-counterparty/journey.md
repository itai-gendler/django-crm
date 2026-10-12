---
{
  "actors": [
    "operator"
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
    }
  ]
}
---

# Inspect consolidated counterparty

## Goal

Inspect consolidation.

## Success criterion

The operator consolidates a Company, Contact person or Lead duplicate, then reaches the corresponding browser with the original counterparty and rewired references retained and the duplicate removed.

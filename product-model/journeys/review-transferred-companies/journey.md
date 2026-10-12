---
{
  "actors": [
    "crm-administrator"
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

# Review transferred companies

## Goal

Inspect bulk transfer.

## Success criterion

The administrator submits selected Companies and a replacement owner, completes the bulk ownership/department changes and reaches the company browser to inspect those records.

---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/tag.py"
    }
  ],
  "relations": [
    {
      "entity": "company",
      "verb": "labels",
      "cardinality": "many-to-many"
    },
    {
      "entity": "lead",
      "verb": "labels",
      "cardinality": "many-to-many"
    },
    {
      "entity": "deal",
      "verb": "labels",
      "cardinality": "many-to-many"
    }
  ]
}
---

# CRM Tag

Name and source-defined CRM applicability/ownership

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Applicability** — Configured subject types on which this tag may be selected.
- **Owner** — The account responsible for this record.
- **Department** — The organizational scope retained on this record.

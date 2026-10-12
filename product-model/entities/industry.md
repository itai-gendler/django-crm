---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/others.py"
    }
  ],
  "relations": [
    {
      "entity": "company",
      "verb": "classifies",
      "cardinality": "many-to-many"
    },
    {
      "entity": "lead",
      "verb": "classifies",
      "cardinality": "many-to-many"
    }
  ]
}
---

# Industry

Name and department; Company/Lead membership

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Department** — The organizational scope retained on this record.

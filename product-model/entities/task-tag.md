---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/tag.py"
    }
  ],
  "relations": [
    {
      "entity": "task",
      "verb": "labels",
      "cardinality": "many-to-many"
    },
    {
      "entity": "project",
      "verb": "labels",
      "cardinality": "many-to-many"
    },
    {
      "entity": "memo",
      "verb": "labels",
      "cardinality": "many-to-many"
    }
  ]
}
---

# Task tag

Name and work-subject applicability

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Applicability** — Configured subject types on which this tag may be selected.

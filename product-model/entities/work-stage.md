---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/stagebase.py"
    }
  ],
  "relations": [
    {
      "entity": "task",
      "verb": "classifies Task",
      "cardinality": "one-to-many"
    },
    {
      "entity": "project",
      "verb": "classifies Project",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Work stage

Name, default, done, in-progress, order and active choices; separate Task and Project applicability relations/configuration collections

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Default** — Marks the configured default choice used by the corresponding operation.
- **Done** — Marks the configured stage used for completed work.
- **In progress** — Marks the configured stage used for work underway.
- **Order** — Configured ordering of the choices.
- **Active** — Whether records using this configured stage remain active.

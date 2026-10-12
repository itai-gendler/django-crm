---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/fixtures/groups.json"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/usermiddleware.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    }
  ],
  "relations": [
    {
      "entity": "user",
      "verb": "includes member",
      "cardinality": "many-to-many"
    }
  ]
}
---

# Permission group

Name, members and configured model-operation permissions

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Members** — Users assigned to this actual Group, including its department association where configured.
- **Permissions** — Model-operation permissions assigned to this Group and inherited by its actual members.

---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    }
  ],
  "relations": [
    {
      "entity": "user",
      "verb": "includes colleague",
      "cardinality": "many-to-many"
    },
    {
      "entity": "request",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "deal",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "company",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "contact-person",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "product",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "project",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "email",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "mailing-out",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Department

Name, members, default country/currency and works-globally choice

## Information kept

- **Name** — The name used to identify the selected record to people.
- **Members** — Users assigned to this actual Group, including its department association where configured.
- **Default country** — Country supplied by mapped department-default branches.
- **Default currency** — Currency supplied by mapped department-default branches.
- **Works globally** — Configured global-operation choice used by inspected department behavior.

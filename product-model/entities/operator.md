---
{
  "acts": "external",
  "kind": "person",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/usermiddleware.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/fixtures/groups.json"
    }
  ],
  "relations": [
    {
      "entity": "user",
      "verb": "has account",
      "cardinality": "one-to-one"
    },
    {
      "entity": "request",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "deal",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "company",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "contact-person",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "lead",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "project",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "memo",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "email",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "email-message",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "mailing-out",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "signature",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "reminder",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "income-snapshot",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "request",
      "verb": "co-owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "deal",
      "verb": "co-owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "co-owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "project",
      "verb": "co-owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "task",
      "verb": "is responsible for",
      "cardinality": "many-to-many"
    },
    {
      "entity": "task",
      "verb": "subscribes to",
      "cardinality": "many-to-many"
    },
    {
      "entity": "project",
      "verb": "is responsible for",
      "cardinality": "many-to-many"
    },
    {
      "entity": "project",
      "verb": "subscribes to",
      "cardinality": "many-to-many"
    },
    {
      "entity": "memo",
      "verb": "receives",
      "cardinality": "one-to-many"
    },
    {
      "entity": "memo",
      "verb": "subscribes to",
      "cardinality": "many-to-many"
    }
  ]
}
---

# Operator

A person acting in the shipped Operator role. Role memberships may overlap and effective model permissions remain configurable.

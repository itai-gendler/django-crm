---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/task.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/taskadmin.py"
    }
  ]
}
---

# Child workflow propagation

A child at In progress reopens a Default parent; an active child reopens an inactive parent to the first In progress stage. Child follow-up edits record on the parent and replace its next step/date only when the parent's step is the initial Task follow-up while the child's is not, or the parent's next-step date is later than the child's. Child stage/completion records the implemented parent entry. Stage/completion of an inactive child invokes exact parent-closure checks and unique attachment copying; later edits of an already closed child also copy unique files. Parent changes are consequences of the successful child operation, not independent direct-edit checks.

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

# Parent completion

After the implemented child stage/completion save, the parent can close automatically only while its stage is Default or In progress, no child remains active and the parent responsible-user set exactly equals the union represented by Done inactive subtasks. The parent uses the first configured Done stage, records automatic closure, changes next step to Done, next step date and closing date to today, and saves Active from stage. Unique child attachment records are copied to the parent without duplicating files already referenced there. Missing stage assumptions have no invented recovery. Project closure is not implied.

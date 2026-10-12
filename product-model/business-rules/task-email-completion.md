---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "user"
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
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/site/tasksbasemodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/create_completed_subtask.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/task_completed.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tests/utils/helpers.py"
    }
  ]
}
---

# Task email completion

Whole-task completion looks up the Task by token and User by URL object_id, authenticates an internal client as that User, obtains native form initials, posts Done and Hide main task, asserts HTTP 200, then renders closed. HTTP 200 can be an unsaved admin form; the closed notice alone does not establish persistence. Team completion FIRST calls check_subtasks(object_id, outer_request), before token/User lookup: URL User ID is used as parent task_id and the outer authenticated caller as responsible. Anonymous callers skip this preflight. Active children produce a warning and browser redirect; qualifying closed hidden children also redirect. The preflight does not use the later token-selected Task or selected User. After lookups the internal client posts a single-responsible Done hidden subtask; returned admin form errors are detected and reported. Missing Task/User uses the not-found responses; internal failures/assertion errors have no invented graceful success. Token lookup, native credentials, available stage/form choices and validation are prerequisites, not retained authorization flags. The source establishes no caller/User relation, identity proof, token/User binding, consent, expiry or single-use enforcement.

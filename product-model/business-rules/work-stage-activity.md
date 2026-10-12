---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "task"
    },
    {
      "type": "entity",
      "id": "project"
    },
    {
      "type": "entity",
      "id": "work-stage"
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
      "target": "tasks/models/project.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/models/stagebase.py"
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

# Work stage activity

Work activity/closing follows configured stage behavior; no automatic Project completion inferred.

Task.clean rejects an inactive submitted stage on a main Task with an active-stage child. The _completed save branch assigns Done after form validation, so this is not an unavoidable guard on every completion path. Task.save derives Active from its stage. Completion/stage change sets closing date where implemented; next-step stage text is replaced when the form did not independently change next step or it retains the initial follow-up. Automatic Project completion is not established.

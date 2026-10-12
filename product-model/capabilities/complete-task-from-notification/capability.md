---
{
  "availability": [
    {
      "place": "crm-web::public"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/task_completed.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/create_completed_subtask.py"
    }
  ],
  "domain": "tasks"
}
---

# Complete task from notification

Process Task-token and URL-selected User lookup, then delegate native mutation to that User through the synthetic client. The link holder remains the actual caller. A closed notice does not prove mutation.

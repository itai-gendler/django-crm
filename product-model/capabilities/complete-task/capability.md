---
{
  "availability": [
    {
      "place": "crm-web::crm-workspace"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "tasks/views/create_completed_subtask.py"
    }
  ],
  "domain": "tasks"
}
---

# Complete task

The authenticated completion path applies its source Task stage operation, with team-part creation handled by its separately catalogued scenario.

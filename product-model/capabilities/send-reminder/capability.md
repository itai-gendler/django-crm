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
      "target": "common/site/reminderadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/utils/reminders_sender.py"
    }
  ],
  "domain": "reminders"
}
---

# Send reminder

Emit notices for due active reminders, optionally email, deactivate and clear related reminder flags. Create missing canonical interval settings when the sender encounters them.

---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-message",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/copy_message.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email message copy permissions

Creates immediate saved reusable-message copy; staff helper.

The actual requesting User passes the active Staff wrapper. The helper reads the supplied source identifier directly, saves a distinct reusable message with the current owner and that account’s default signature or none, then opens its editor. It performs no native source View, ownership or target Add check; later native editing retains its own checks.

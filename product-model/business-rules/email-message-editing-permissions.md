---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email-message",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-message-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/email_message.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmmodeladmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/clarify_permission.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email message editing permissions

Native reusable-message effective model permission, the actual queryset and ownership clarification checks; saved-copy helper excluded

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

The native site requires active Staff access. Native Add uses effective Add; native View uses View or Change; Change/Delete use their corresponding effective permission. Lookup uses selected department first, otherwise Superoperator assigned department Groups, otherwise the base queryset. Object Change/Delete applies clarify_permission in its implemented Chief/Superoperator/Superuser, matching Operator department, then owner/co-owner order. Separate copy/preview helpers retain their own checks.

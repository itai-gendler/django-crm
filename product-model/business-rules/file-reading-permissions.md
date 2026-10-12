---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "file",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::deal-record"
        },
        {
          "place": "crm-web::crm-workspace::task-record"
        },
        {
          "place": "crm-web::crm-workspace::project-record"
        },
        {
          "place": "crm-web::crm-workspace::memo-record"
        },
        {
          "place": "crm-web::crm-workspace::email-record"
        },
        {
          "place": "crm-web::crm-workspace::email-message-record"
        },
        {
          "place": "crm-web::crm-workspace::company-record"
        },
        {
          "place": "crm-web::crm-workspace::contact-person-record"
        },
        {
          "place": "crm-web::crm-workspace::lead-record"
        },
        {
          "place": "crm-web::crm-workspace::request-record"
        },
        {
          "place": "crm-web::crm-workspace::product-record"
        },
        {
          "place": "crm-web::crm-workspace::transaction-quality-event-record"
        },
        {
          "place": "crm-web::crm-workspace::chat-thread"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/models.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "common/admin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# File reading permissions

Inline add/change/delete normally use File change permission plus ordered host clarification. An unreviewed Memo’s recipient has the explicit Add exception. Link presentation follows host disclosure; no private byte-delivery policy is asserted

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

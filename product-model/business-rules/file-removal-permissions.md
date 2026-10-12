---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "file",
      "effect": "removes",
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

# File removal permissions

Inline add/change/delete normally use File change permission plus ordered host clarification. An unreviewed Memo’s recipient has the explicit Add exception. Link presentation follows host disclosure; no private byte-delivery policy is asserted

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

For ordinary inline changes, common.change_thefile is checked first. Host clarification accepts its owner or an ownerless host unless that branch finds Reviewed Memo, Incoming/UID Email, or ownerless Chief; that early refusal is retained. A host without owner is accepted. Otherwise it accepts co-owner, Superoperator, Task operator, Superuser, matching-department Operator, its sole responsible participant, or Chief for a Deal-like host; otherwise it refuses. Add has the explicit unreviewed Memo recipient exception before the ordinary change check; Delete delegates to change. The inline collects only the file upload. Other host facts and attachment attribution follow the initiating save/copy path.

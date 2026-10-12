---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "email",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::email-record"
        }
      ]
    },
    {
      "type": "entity",
      "id": "email",
      "effect": "changes",
      "facts": [
        "Deal"
      ],
      "contexts": [
        {
          "place": "crm-web::crm-workspace::request-record"
        }
      ]
    },
    {
      "type": "entity",
      "id": "email",
      "effect": "changes",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::lead-record"
        }
      ],
      "facts": [
        "Lead",
        "Company",
        "Contact person"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/crmemail.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/crmemailadmin.py"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Email editing permissions

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

For CRM change, first obtain the inherited change result, which includes native model permission and inherited CRM clarification. If it is false, a Manager who owns/co-owns the linked Deal returns true immediately; otherwise return that false result. Only if the inherited result was true, incoming or UID-bearing correspondence is refused; remaining correspondence passes ordered clarify_permission. The fallback precedes the Incoming/UID veto and can override a false inherited result; no unconditional change_crmemail conjunct is added. Native object lookup still uses the CRM queryset. Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. 

Request-derived Deal ticket-link updates and Lead conversion reference rewiring follow their initiating permitted operations, without independent Email change checks. Automatic Sent follows authorized native Email Add/Change save and the sending rule.

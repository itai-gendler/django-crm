---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "signature",
      "effect": "reads",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::signature-record"
        },
        {
          "place": "crm-web::crm-workspace::signature-browser"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/signature.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/signatureadmin.py"
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
      "target": "common/site/basemodeladmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    }
  ]
}
---

# Signature reading permissions

Native Signature effective model permission, the actual queryset and ownership clarification checks; preview helper excluded

Configuration means the actual account evaluated by this handler: its retained direct permissions, assigned Group permissions, Active/Staff/Superuser configuration and derived overlapping role flags. Effective native permissions include Group inheritance and native superuser handling; an unrelated User or Group never supplies authority.

Native CRM object lookup uses the selected department first; otherwise a Superoperator is restricted to assigned department Groups; otherwise the queryset is unfiltered. Ordered clarification accepts Chief, Superoperator or Superuser first; then Operator with matching selected department; then actual owner/co-owner, otherwise refuses. Native Add uses effective Add; native view uses effective View or Change; native change/delete requires its corresponding permission before clarification when an object is supplied.

BaseModelAdmin ID and ticket search branches replace the preceding queryset with the model-wide matching queryset; the ordinary search branch uses the supplied queryset. Do not carry the earlier list filtering into the replacing branches.

The native site requires active Staff access. Native Add uses effective Add; native View uses View or Change; Change/Delete use their corresponding effective permission. Lookup uses selected department first, otherwise Superoperator assigned department Groups, otherwise the base queryset. Object Change/Delete applies clarify_permission in its implemented Chief/Superoperator/Superuser, matching Operator department, then owner/co-owner order. Separate copy/preview helpers retain their own checks.

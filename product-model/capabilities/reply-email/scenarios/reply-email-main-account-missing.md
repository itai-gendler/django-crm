---
{
  "kind": "edge",
  "routes": {
    "main": "Reply Email — main account missing"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The account whose main email account is needed by this operation has none.",
      "entities": [
        {
          "entity": "email-account",
          "effect": "reads",
          "facts": []
        }
      ],
      "actor": "operator"
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke reply.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [],
          "as": "source-correspondence"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "Missing main account is reported without establishing the intended draft/routing.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To"
          ],
          "as": "source-correspondence"
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::email-record"
        }
      },
      "actor": "operator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/views/reply_email.py"
    }
  ]
}
---

# Reply Email — main account missing

## Trigger

Operator invokes Reply Email.

## Outcome

Missing main account is reported without establishing the intended draft/routing.

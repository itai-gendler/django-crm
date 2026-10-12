---
{
  "kind": "edge",
  "routes": {
    "main": "Send Email — smtp failure"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The correspondence send raises one of the exceptions caught in the send block.",
      "entities": []
    },
    {
      "kind": "actor",
      "actor": "operator",
      "text": "Select Email in CRM and invoke send.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": []
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
      "text": "The caught SMTP/header/address failure returns to the saved draft with its failure notice and without the final Sent save. An external attempt may already have occurred, so delivery remains uncertain.",
      "entities": [
        {
          "entity": "email",
          "effect": "reads",
          "facts": [
            "Subject",
            "Content",
            "Sender",
            "To"
          ]
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
      "target": "crm/site/crmemailadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/utils/send_email.py"
    }
  ]
}
---

# Send Email — smtp failure

## Trigger

Operator invokes Send Email.

## Outcome

The caught SMTP/header/address failure returns to the saved draft with its failure notice and without the final Sent save. An external attempt may already have occurred, so delivery remains uncertain.

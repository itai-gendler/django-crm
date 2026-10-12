---
{
  "kind": "edge",
  "routes": {
    "main": "Send mailing out — unsubscribed queue entry"
  },
  "steps": [
    {
      "kind": "condition",
      "text": "The pending recipient registration is no longer mailing-eligible.",
      "entities": [],
      "unattended": true,
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      }
    },
    {
      "kind": "product",
      "text": "The ineligible pending registration is not sent; queue completion is not guaranteed.",
      "entities": [
        {
          "entity": "mailing-out",
          "effect": "reads",
          "facts": [
            "Name",
            "Message",
            "Recipient type",
            "Status"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/admin_actions.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/utils/sendmassmail.py"
    }
  ]
}
---

# Send mailing out — unsubscribed queue entry

## Trigger

The configured processing condition occurs.

## Outcome

The ineligible pending registration is not sent; queue completion is not guaranteed.

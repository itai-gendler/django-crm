---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out",
      "effect": "creates",
      "contexts": [
        {
          "place": "crm-web::crm-workspace::mailing-out-record"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/models/mailing_out.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    }
  ],
  "permits": []
}
---

# Mailing out direct add prohibition

Ordinary Mailing Out native Add is forbidden; selected-counterparty, filtered and merged creation have separate initiating-operation policies.

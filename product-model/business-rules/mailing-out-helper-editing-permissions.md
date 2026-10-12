---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "mailing-out",
      "effect": "changes",
      "facts": [
        "Pending recipients",
        "Failed recipients",
        "Recipient count"
      ],
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
      "target": "massmail/views/exclude.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/views/send_failed_recipients.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "massmail/site/mailingoutadmin.py"
    }
  ],
  "permits": [
    {
      "configuredBy": "user"
    },
    {
      "unattended": true,
      "when": [
        {
          "entity": "product-settings",
          "fact": "Mailing enabled",
          "is": true
        },
        {
          "entity": "product-settings",
          "fact": "Testing",
          "is": false
        },
        {
          "entity": "mailing-settings",
          "fact": "Daily account limit",
          "present": true
        }
      ]
    }
  ]
}
---

# Mailing out helper editing permissions

Changes failed/pending/excluded recipients through helpers; staff wrapper without additional owner/model checks.

Human recipient retry/exclusion handlers use the actual requesting User’s active Staff wrapper, with no additional campaign-owner or native model Change check. Unattended queue mutations retain the sender’s configured operating gates and campaign/account routing.

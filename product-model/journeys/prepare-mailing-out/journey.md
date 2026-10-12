---
{
  "actors": [
    "sales-manager"
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

# Prepare mailing out

## Goal

Prepare campaign.

## Success criterion

The sales manager creates a campaign from selected or filtered counterparties, reaches its retained campaign record and saves its message/status choices.

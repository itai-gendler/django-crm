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

# Continue merged mailing out

## Goal

Continue merged campaign.

## Success criterion

The sales manager reaches the newly merged campaign after originals are removed, then edits and saves that campaign’s message/status choices.

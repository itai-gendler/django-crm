---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "deal"
    },
    {
      "type": "entity",
      "id": "closing-reason"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/deal.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/models/others.py"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "crm/site/dealadmin.py"
    }
  ]
}
---

# Deal closing reason

Closing reason controls activity; successful reason sets success stage/dates; clearing reason clears closing date without clearing retained win time.
